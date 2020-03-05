# Pantheon repository for ECP Artifacts
Pantheon aims to provide immutable, reproducible, and reusable experiment pipelines on target infrastructures. Each pipeline will produce at least one research artifact.
 
## Pantheon provides reproducibility for exploratory research
Early software development efforts have unique build requirements and suffer from inconsistent versioning practices. The focus of Pantheon is to capture the state of a working experiment, to demonstrate a proof of concept. 

## Software dependencies
1. Add SSH key from your target infrastructure to your GitHub account [Documentation](https://help.github.com/en/articles/adding-a-new-ssh-key-to-your-github-account)
2. Add Pantheon-popper to a pantheon environment on Summit (copy-paste is recommended):
```
module load python;
module load py-virtualenv;
cd;
virtualenv -p python3.6 venv/pantheon;
source venv/pantheon/bin/activate;
# First install will partially fail
pip install popper==2.4.2;
# Second install will succeeed
pip install popper==2.4.2;
export LC_ALL=en_US.utf8
```

## How to use Pantheon
1. Grab an allocation before running the experiment. The pipeline builds in parallel, which means we aren't allowed to build on Summit login nodes. Example allocation:
```
bsub -W 50 -nnodes 1 -P CSC340 -Is /bin/bash
```
1. Clone this repository recursively:
```
git clone --recursive git@github.com:pantheonscience/ECP-Artifacts.git
```
2. Activate your Pantheon Python environment:
```
source ~/venv/pantheon/bin/activate;
export LC_ALL=en_US.utf8
```
3. Descend into an experiment directory, which will contain `main.workflow`.
4. Information about this experiment will be described in the README.
5. After reading the experiment description, execute `popper run` from this directory.
6. When the pipeline successfully completes, the path to the research artifact(s) will be written to STDIO.
7. (Optional) When you are finished with your Pantheon Python environment, deactivate it:
```
deactivate;
```
