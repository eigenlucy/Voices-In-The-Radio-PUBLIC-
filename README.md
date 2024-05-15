# Voices-In-The-Radio-PUBLIC-
A system agnostic guide to fine tuning openai GPT models using Conda and Docker based on the workflow used in our Opensauce 2024 project "Voices in the Radio"

# clone this repo
# conda
## install conda
conda is a tool for python enviroment virtualization and management. this will manage our pypi python packages and libraries for us in whatever OS we like. you can use anaconda or miniconda. follow the install instructions for your system: https://docs.anaconda.com/free/distro-or-miniconda/

## create and activate a conda enviroment named "voices"
create an enviroment called voices using `conda create -n voices`

list your conda enviroments `conda info --envs`. the active enviroment is indicated with an asterisk(*).

enter the voices enviroment with `conda activate voices`

**Use `conda activate` to return to the base enviroment later on when you are done working on this project.**

# docker
## install docker engine
docker provides provides a container with linux and python 3.10 installed, required libraries, and the setup for chromedriver. follow the install guide for your OS detailed here: https://docs.docker.com/engine/install/

verify docker's status by ensuring `docker info` returns client information

## docker configuration

build the docker container with `docker build -t voices .`

Mount local files to container and run bash on it with `docker run -it -p 4000:4000 -v $(pwd):/usr/src/app voices /bin/bash`

# create a .env file containing your openai api key