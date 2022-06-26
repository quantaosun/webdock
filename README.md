# Free_Cloud_Docking

Updated on 26 June 2022. Initial docking, then MD to relax the binding pose, then use this relaxed pose as a new starting point for another flexible docking by Vina, at last one more MD is designed to give both final binding pose and MMPBS score of binding.

Updated on 14 May 2022, Selectivity prediction docking procedure added. 2 ligands will be docked to two close related protein targets, to address how selectivity would change upon chemical modification from ligand 1 to ligand 2, towards target 1 to target 2.

![image](https://user-images.githubusercontent.com/75652473/168420589-deb81559-c4fe-443a-a9c1-74c3afb4cff9.png)

If you have to get a perfect docking result, you are suggested to yield the 4 docked top1 poses subject to https://github.com/pablo-arantes/making-it-rain/blob/main/Protein_ligand.ipynb to do a short MD simulation, to further tune the pocket interaction with your ligand bound. After that, you can run this 00298075 notebook again but with the bound ligand itself, this way, you realized a so-called "Induced Fit Docking" or even better.

What's more, this 00298075 notebook also enables two potential pairwise FEP calculations, i.e., FEP of ligand 1 changed to ligand 2 on target1, and ligand 1 changed to ligand 2 on target 2. But that would be another topic. You can head to https://github.com/quantaosun/NAMD-FEP to have a general idea how what it looks like.

What excited me the most is the fact, that what is provided here, does not request you anything but a google account and a computer connected to the internet, let's say you are in a public library providing computers, as long as you can log in to your Google account, you don't even have to have your own laptop, you still can finish all the content included in 00298075 and https://github.com/pablo-arantes/making-it-rain/blob/main/Protein_ligand.ipynb. That is to say, you nearly don't have to spend a cent but can do some state-of-the-art (2022) medicinal modelling. Of course, there are better methodologies that exist, but they cost hugely sometimes.

---------------------------------------------------------------------------------------------------------------------------------------------------------
# I will be sad if you ever decide to use this on a local computer, the whole point here is to use docking on the cloud. But it is definitely possible if you insist on using it locally.

Molecular docking is the simplest yet one of the most powerful methods of modelling in the medicinal chemistry field. There are many licensed and free academic options there, but most still need a local installation. This is a cloud pipeline based on Autodock Vina (Smina), aiming to provide a totally free tool to those who want to use molecular docking in their projects. You don't have to install anything but provide an SDF file that could be from Chemdraw and a protein RCSB four-letter code.

 References and contribution elaboration
 This code was first inspired by [https://www.macinchem.org/reviews/JupyterDocking/jupyterdocking.php](http://) and [https://www.cheminformania.com/ligand-docking-with-smina/](http://)


The following was changed in this notebook compared to the above two:
1. This notebook provides docking with a pocket water option compared to the original one, what I have done is use Pymol to keep 5 of the ligand then use the water-contained receptor in docking. There are two cells, you should only run one of them, be careful! 

Docking without waters

```
com_file = open('fetch_and_clean.pml','w')
com_file.write('''
load 1234.pdb
remove resn HOH
h_add elem O or elem N
select 1234-567, resn 567 #Create a selection called 1234-567from the ligand
select 1234-receptor, 1234 and not 1234-567 #Select all that is not the ligand
save 1234-567.pdb, 1234-567
save 1234-receptor.pdb, 1234-receptor    
''')
com_file.close()
```
OR, with waters.

```
com_file = open('fetch_and_clean.pml','w')
com_file.write('''
load 1234.pdb
create ligand= resn 567 
create active_water= resn HOH within 5 of ligand
remove resn HOH &! active_water
h_add elem O or elem N
select 1234-567, resn 567 #Create a selection called 1234-567 from the ligand
select 1234-receptor, 1234 and not 1234-567 #Select all that is not the ligand
save 1234-567.pdb, 1234-567
save 1234-receptor.pdb, 1234-receptor    
''')
com_file.close()
```

2. The docking validation and docking separately existed in two non-related notebooks, but this one integrated them in a single notebook, which will save time and be more convenient.
1. If you use this notebook on AI Studio(https://aistudio.baidu.com/aistudio/index), it realized the "permanent" installation, unlike the google collab in which you have to install each time before you could do anything. 

3. Conda, Pymol and three to four paths have been modified to maintain the compatibility on Colab, but with extra AI studio compatibility, you may find the path a bit weird on Colab, that is to get rid of some user restrictions from AI studio, it will still work on Colab. 
