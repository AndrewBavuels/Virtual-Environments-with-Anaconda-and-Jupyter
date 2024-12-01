#### (Work in progress from local to GitHub)

(A commit test from GitHub)

# Virtual Environments with Anaconda and Jupyter

## Create virtual environments from scratch
 ```sh

andrewbavuels@the-Legionnaire:~/virtual_envs$ pwd
/home/andrewbavuels/virtual_envs

andrewbavuels@the-Legionnaire:~/virtual_envs$ python3 -m venv pilot_env
 ```

## Activate the virtual environment

```sh
andrewbavuels@the-Legionnaire:~/virtual_envs$ source pilot_env/bin/activate

(pilot_env) andrewbavuels@the-Legionnaire:~/virtual_envs$
```

## Deactivate the virtual environment

```sh
(pilot_env) andrewbavuels@the-Legionnaire:~/virtual_envs$ deactivate

andrewbavuels@the-Legionnaire:~/virtual_envs$
```

## Remove virtual environments

```sh
rm -rf pilot_env
```
## Install packages or libraries in your virtual environment

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

## When to use Anaconda?

In data science and machine learning projects when you need libraries like TensorFlow or PyTorch, to simplify your specific configuration and versions.

[Conda cheat sheet](https://docs.conda.io/projects/conda/en/4.6.0/_downloads/52a95608c49671267e40c689e0bc00ca/conda-cheatsheet.pdf)

### Creating virtual environments with Anaconda


