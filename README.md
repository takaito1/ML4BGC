# Machine Learning for Biogeochemistry (ML4BGC)

## Setting up the python environment
  - Install miniconda3 on your cluster account
  - Initialize conda command
```
mkdir -p ~/miniconda3
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O ~/miniconda3/miniconda.sh
bash ~/miniconda3/miniconda.sh -b -u -p ~/miniconda3
rm -rf ~/miniconda3/miniconda.sh
source ~/miniconda3/etc/profile.d/conda.sh
conda activate
```
  - Then create a new environment called ml4o2_v2.  
```
conda create --name ml4o2_v2
```
  - Then activate ml4o2_v2.
```
conda activate ml4o2_v2
```
  - Then install mamba in ml4o2_v2.
```
conda install -c conda-forge mamba
```
  - Install packages manually
```
mamba install -c conda-forge numpy matplotlib pandas netcdf4 dask nc-time-axis cartopy seaborn gsw xarray scikit-learn scipy joblib ipykernel
```
  - Once it is complete, make this environment available to the Jupyter Notebook:
```
python -m ipykernel install --user --name ml4o2_v2 --display-name ML4O2_v2
```
  - At this point the "ML4O2_v2" environment should be ready to use in Jupyterlab/Jupyter Notebook.

## Xarray tutorial
- This video is a good introduction to X array [link](https://youtu.be/a339Q5F48UQ?si=mcCZE2vuptlOZPuE) Please watch this video if you haven't do so already.

## PO4 project instructions
  - PO4/src : source codes
  - PO4/run : this is where we run the job

  - First, download this repository. 
```
git clone https://github.com/takaito1/ML4BGC.git
```
  - Create a space to hold the output by replacing the "username" with your account
```
mkdir -p /glade/derecho/scratch/username/ML4BGC_results/
mkdir -p /glade/derecho/scratch/username/ML4BGC_temp/
```
  - Then, edit the following files for specific user
  - In PO4/src/run.pbs, edit line 9, 11, and 14 for your account
  - In PO4/src/po4_trian.py, edit line 36 and 114 for your account
  - In PO4/src/po4_eval.py, edit line 21 and 22 for your account
  - In PO4/src/po4_project.py, edit line 34 and 109 for your account
```
cd PO4/run
```
  - run the jupyter notebook "gen_exec.ipynb"
  - this will create the executable file, "exec.sh"
  - you have to ssh into derecho using your credential
```
ssh derecho
```
  - then you can execute the run script
```
bash exec.sh
```
  - you can check the status of the run using "qstat"
```
qstat
```
