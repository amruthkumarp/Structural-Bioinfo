#modeller
#blast a given sequence using blastp against protein databses
find the best hit with most coverge and identity
download the pdb structure
#remove seqres first and connect 

#pymol
load yourfile.pdb
alter resn MSE, resn='MET'          
alter name SE, name='SD'         
save yourfile_met.pdb

#remove HETATM and connect
#make .pir file of qurey sequence 
#use pir.py replace pdb and pir file to generate the .ali file
#run modeller on that file to generate pdb structures

#clean the pdb file
delete seqres records
clean pdb change selenomethionine and clean pdb
remove hetatm and connect, only retain chain A 

#activating obebal
conda activate obabel_env
obabel -ismi my_structure.smi -o pdb -O my_structure_3D.pdb --gen3d

#convert png to smi
osra my_structure.png -o my_structure.smi
use online https://cactus.nci.nih.gov/cgi-bin/osra/index.cgi

#ccp
source /home/ibab/ccp4/ccp4-7.0/bin/ccp4.setup-sh

#binding pokects 
https://cfold.bme.uic.edu/castpfold/compute

#Autodockvina
vina --config ligand2_vina_config.txt --out ligand2_out.pdbqt 
vina_split --input ligand2_out.pdbqt



