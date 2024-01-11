
![image](https://github.com/quantaosun/webdock/assets/75652473/383505bd-ee59-4c84-8cd0-a3355af828fd)

## Try webdock on the "Cloud"

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/quantaosun/webdock/HEAD?labpath=mybinder-1.ipynb)

## Installing webdock locally, on a Linux or Mac

```
git clone https://github.com/quantaosun/webdock.git
cd webdock
```
By downloading this repo, comes inside an environment.yml file, before you could create an identical envrionment as required, check out your conda path

```
conda env list
```
Let say the output is 
```
/home/anaconda/env
```
Then modify the last line of environment.yml, the prefix path, to the output of the listed conda envs base

That is to say, it is recommanded you change ```prefix: /srv/conda/envs/notebook``` to ```prefix: /home/anaconda/env```.

You may also want to change the env name from ```notebook``` to ```webdock```, in the first line, it doesn't matter to our purpuse of docking, but just for being descriptive.

then create the environment by

```
conda env create -f environment.yml
```
After finishing, it is ready to go

```
conda activate webdock
```
Now launch the jupyter notebook

```
jupyter notebook webdock_v.0.0.2.ipynb
```
You should then be able to run an exactly the same notebook with the same environment settings, locally






 






