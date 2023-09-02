## The most reliabe manner to use pl3 is always to install it locally, as shown inside the folder
But if you just want to use it in a light manner,you can use it on Binder (public free server)
## Try a quick docking online 

[![Binder](https://notebooks.gesis.org/binder/jupyter/user/quantaosun-pl3-plx8e46h/doc/tree/mybinder.ipynb)]

If using this in a local Unix machine from within an independent conda channel, add the following to the notebook (you need change the path accordingly)

```
import sys
sys.path.append('/root/miniconda3/envs/pl3/lib/python3.8/site-packages')

```

After mybinder.ipynb you will get complex1.pdb and a file called complex1.sdf, using these two files you can do a molecular dynamics after charmmgui solution builder, with NAMD on colab.

## MD simulation of docked pose 1 on Google Colab with NAMD

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/quantaosun/pl3/blob/main/charmgui_namd3_simulation_after_mybinder_pl3.ipynb)


## To dock a list of small molecules, Open in Colab

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/quantaosun/pl3/blob/main/Free_Cloud_Docking_multiple_docking.ipynb)
                                                                                                  

![image](https://user-images.githubusercontent.com/75652473/216478725-1e67edce-b939-4dca-a147-4e5688e53240.png)


 






