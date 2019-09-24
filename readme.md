# Pantheon repository for ECP Artifacts
Pantheon aims to provide immutable, reproducible, and reusable experiment pipelines. 
 
## Pantheon provides reproducibility for exploratory research
Early software development efforts have unique build requirements and suffer from inconsistent versioning practices. The focus of Pantheon is to capture the state of a working experiment, to demonstrate a proof of concept. 

## Software dependencies
Pantheon establishes reproducible experiment pipelines for target infrastructures. You will need to add Popper v2.3.0+ to your Python environment. Popper is used to execute and manage all Pantheon experiment pipelines. Further dependencies are resolved by the pipeline.

## How to use Pantheon
1. Clone this repository recursively:
``` git clone --recursive git@github.com:pantheonscience/ECP-Artifacts.git```.
2. Descend into the experiment directory, which will contain `main.workflow`.
3. Information about this experiment will be described in the README.
3. After reading the experiment description, execute `popper run` from this directory.
4. When the pipeline successfully completes, the path to a research artifact will be written to STDIO.
