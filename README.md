# Virtual Environments with Anaconda and Jupyter

## 1. Create virtual environments from scratch (without Anaconda)

To create a virtual environment using `venv`, navigate to the desired directory and run:

 ```sh
andrewbavuels@the-Legionnaire:~/virtual_envs$ pwd
/home/andrewbavuels/virtual_envs

andrewbavuels@the-Legionnaire:~/virtual_envs$ python3 -m venv pilot_env
 ```

### Activate the virtual environment

```sh
andrewbavuels@the-Legionnaire:~/virtual_envs$ source pilot_env/bin/activate
fff
(pilot_env) andrewbavuels@the-Legionnaire:~/virtual_envs$
```

### Deactivate the virtual environment

```sh
(pilot_env) andrewbavuels@the-Legionnaire:~/virtual_envs$ deactivate

andrewbavuels@the-Legionnaire:~/virtual_envs$
```

### Remove virtual environments

```sh
rm -rf pilot_env
```
### Install packages or libraries in your virtual environment

```sh
(pilot_env) andrewbavuels@the-Legionnaire:~/virtual_envs$ pip install pandas matplotlib
Collecting pandas
Downloading pandas-2.2.3-cp310-cp310-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (13.1 MB)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 13.1/13.1 MB 17.9 MB/s eta 0:00:00
...
```
**How to check if we have the packages in the virtual environment?**

```sh (pilot_env) andrewbavuels@the-Legionnaire:~/virtual_envs$ python3 Python 3.10.12 (main, Sep 11 2024, 15:47:36) [GCC 11.4.0] on linux Type "help", "copyright", "credits" or "license" for more information.
>>> import pandas >>> import matplotlib >>> exit() (pilot_env) andrewbavuels@the-Legionnaire:~/virtual_envs$ deactivate andrewbavuels@the-Legionnaire:~/virtual_envs$ import pandas -bash: import: command not found 
``` 
## Wrap up:

- `python3 -m venv <env_name>`: Creates a virtual environment.
- `source <env_name>/bin/activate`: Activates the virtual environment.
- `deactivate`: Deactivates the virtual environment.
- `rm -rf <env_name>`: Removes the virtual environment.
- `pip install <package_name>`: Installs packages in the virtual environment.

## 2. When to use Anaconda?

In data science and machine learning projects when you need libraries like TensorFlow or PyTorch, to simplify your specific configuration and versions.

[Conda cheat sheet](https://docs.conda.io/projects/conda/en/4.6.0/_downloads/52a95608c49671267e40c689e0bc00ca/conda-cheatsheet.pdf)

### Creating virtual environments with Anaconda

```sh
andrewbavuels@the-Legionnaire:~/virtual_envs$ conda create --name example
```
### Activate the virtual environment

```sh
andrewbavuels@the-Legionnaire:~/virtual_envs$ conda activate example
(example) andrewbavuels@the-Legionnaire:~/virtual_envs$
```

### Check the Python version by default

```sh
(example) andrewbavuels@the-Legionnaire:~/virtual_envs$ python3
Python 3.10.12 (main, Sep 11 2024, 15:47:36) [GCC 11.4.0] on linux
...
>>> exit()
```
### Deactivate the virtual environment

```sh
(example) andrewbavuels@the-Legionnaire:~/virtual_envs$ conda deactivate
andrewbavuels@the-Legionnaire:~/virtual_envs$
```

### Creating another virtual environment specifying Python version to 3.9

```sh
andrewbavuels@the-Legionnaire:~/virtual_envs$ conda create --name example_2 python=3.9
```
### Repeating previous steps:  

#### Activating example_2 env:

```sh
andrewbavuels@the-Legionnaire:~/virtual_envs$ conda activate example_2
```
#### Checking Python version:

```sh
(example_2) andrewbavuels@the-Legionnaire:~/virtual_envs$ python3
Python 3.9.20 (main, Oct  3 2024, 07:27:41)
```

#### Deactivating example_2 env:

```sh
(example_2) andrewbavuels@the-Legionnaire:~/virtual_envs$ conda deactivate
```

### Checking created envs so far

```sh
andrewbavuels@the-Legionnaire:~/virtual_envs$ conda env list

# conda environments:
#
base                   /home/andrewbavuels/anaconda3
example                /home/andrewbavuels/anaconda3/envs/example
example_2              /home/andrewbavuels/anaconda3/envs/example_2
jupyter                /home/andrewbavuels/anaconda3/envs/jupyter
keras_env              /home/andrewbavuels/anaconda3/envs/keras_env
pandas_numpy_env       /home/andrewbavuels/anaconda3/envs/pandas_numpy_env
pentaho_env            /home/andrewbavuels/anaconda3/envs/pentaho_env
```
### Install packages or libraries in your virtual environment

```sh
andrewbavuels@the-Legionnaire:~/virtual_envs$ conda activate example

(example) andrewbavuels@the-Legionnaire:~/virtual_envs$ conda install numpy pandas
```
**How to check if we have the packages in the virtual environment?**

```sh
Type "help", "copyright", "credits" or "license" for more information.
>>> import numpy as np
>>> import pandas as pd
>>>
```

### Checking libraries and packages installed in env "example"

```sh
(example) andrewbavuels@the-Legionnaire:~/virtual_envs$ conda deactivate
andrewbavuels@the-Legionnaire:~/virtual_envs$ conda list -n example_2
# packages in environment at /home/andrewbavuels/anaconda3/envs/example_2:
#
# Name                    Version                   Build  Channel
_libgcc_mutex             0.1                        main
_openmp_mutex             5.1                       1_gnu
ca-certificates           2024.11.26           h06a4308_0
ld_impl_linux-64          2.40                 h12ee557_0
libffi                    3.4.4                h6a678d5_1
libgcc-ng                 11.2.0               h1234567_1
libgomp                   11.2.0               h1234567_1
libstdcxx-ng              11.2.0               h1234567_1
ncurses                   6.4                  h6a678d5_0
openssl                   3.0.15               h5eee18b_0
pip                       24.2             py39h06a4308_0
python                    3.9.20               he870216_1
readline                  8.2                  h5eee18b_0
setuptools                75.1.0           py39h06a4308_0
sqlite                    3.45.3               h5eee18b_0
tk                        8.6.14               h39e8969_0
tzdata                    2024b                h04d1e81_0
wheel                     0.44.0           py39h06a4308_0
xz                        5.4.6                h5eee18b_1
zlib                      1.2.13               h5eee18b_1
```
As you can see, there is not pandas nor numpy in this env.

Now with **example**:

```sh
andrewbavuels@the-Legionnaire:~/virtual_envs$ conda list -n example
# packages in environment at /home/andrewbavuels/anaconda3/envs/example:
#
# Name                    Version                   Build  Channel
_libgcc_mutex             0.1                        main
_openmp_mutex             5.1                       1_gnu
blas                      1.0                         mkl
bottleneck                1.4.2           py313hf0014fa_0
bzip2                     1.0.8                h5eee18b_6
ca-certificates           2024.11.26           h06a4308_0
expat                     2.6.3                h6a678d5_0
intel-openmp              2023.1.0         hdb19cb5_46306
ld_impl_linux-64          2.40                 h12ee557_0
libffi                    3.4.4                h6a678d5_1
libgcc-ng                 11.2.0               h1234567_1
libgomp                   11.2.0               h1234567_1
libmpdec                  4.0.0                h5eee18b_0
libstdcxx-ng              11.2.0               h1234567_1
libuuid                   1.41.5               h5eee18b_0
mkl                       2023.1.0         h213fc3f_46344
mkl-service               2.4.0           py313h5eee18b_1
mkl_fft                   1.3.11          py313h5eee18b_0
mkl_random                1.2.8           py313h06d7b56_0
ncurses                   6.4                  h6a678d5_0
numexpr                   2.10.1          py313h3c60e43_0
numpy                     2.1.3           py313hf4aebb8_0
numpy-base                2.1.3           py313h3fc9231_0
openssl                   3.0.15               h5eee18b_0
pandas                    2.2.3           py313h6a678d5_0
pip                       24.2            py313h06a4308_0
python                    3.13.0          hf623796_100_cp313
python-dateutil           2.9.0post0      py313h06a4308_2
python-tzdata             2023.3             pyhd3eb1b0_0
python_abi                3.13                    0_cp313
pytz                      2024.1          py313h06a4308_0
readline                  8.2                  h5eee18b_0
setuptools                72.1.0          py313h06a4308_0
six                       1.16.0             pyhd3eb1b0_1
sqlite                    3.45.3               h5eee18b_0
tbb                       2021.8.0             hdb19cb5_0
tk                        8.6.14               h39e8969_0
tzdata                    2024b                h04d1e81_0
wheel                     0.44.0          py313h06a4308_0
xz                        5.4.6                h5eee18b_1
zlib                      1.2.13               h5eee18b_1
```
### Removing libraries and packages installed in env "example"

- First, you need to be in the corresponding env (in this case, "example" env):

```sh
(example) andrewbavuels@the-Legionnaire:~/git_github/RECYCLE$ conda remove pandas numpy
```

### Clean cache of packages we are not using anymore

```sh
(example) andrewbavuels@the-Legionnaire:~/git_github/RECYCLE$ conda clean --packages
Will remove 57 (331.7 MB) package(s).
Proceed ([y]/n)?```

```sh
(example) andrewbavuels@the-Legionnaire:~/git_github/RECYCLE$ conda clean --all
Will remove 882 (2.16 GB) tarball(s).
Proceed ([y]/n)?
```
### Removing environments

- Deactivate the current environment (if active):

```sh
(example) andrewbavuels@the-Legionnaire:~/git_github/RECYCLE$ conda deactivate
```
- List all environments:

```sh
andrewbavuels@the-Legionnaire:~/git_github/RECYCLE$ conda env list

base                   /home/andrewbavuels/anaconda3
example                /home/andrewbavuels/anaconda3/envs/example
example_2              /home/andrewbavuels/anaconda3/envs/example_2
jupyter                /home/andrewbavuels/anaconda3/envs/jupyter
keras_env              /home/andrewbavuels/anaconda3/envs/keras_env
pandas_numpy_env       /home/andrewbavuels/anaconda3/envs/pandas_numpy_env
pentaho_env            /home/andrewbavuels/anaconda3/envs/pentaho_env
```
- Remove the specified environments:

```sh
andrewbavuels@the-Legionnaire:~/git_github/RECYCLE$ conda remove --name example example_2 pentaho_env --all
```

## Wrap up:

- `conda create --name <env_name>`: Creates a virtual environment with Anaconda.
- `conda activate <env_name>`: Activates the Anaconda environment.
- `conda deactivate`: Deactivates the Anaconda environment.
- `conda create --name <env_name> python=<version>`: Creates an environment with a specific Python version.
- `conda env list`: Lists all environments created by Anaconda.
- `conda install <package_name>`: Installs packages in an Anaconda environment.
- `conda list -n <env_name>`: Lists installed packages in a specific Anaconda environment.
- `conda remove <package_name>`: Removes specific packages from an environment.
- `conda clean --packages`: Cleans up unused package caches.
- `conda clean --all`: Cleans all unnecessary files, including tarballs.
- `conda remove --name <env_name> --all`: Removes an Anaconda environment completely.

# Coming up next (conda update)...