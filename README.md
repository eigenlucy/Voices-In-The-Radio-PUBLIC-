# **UNDER CONSTRUCTION** Voices In The Radio **UNDER CONSTRUCTION**
A system agnostic guide to [fine tuning GPT models](https://platform.openai.com/docs/guides/fine-tuning) using Conda and Docker based on the workflow used in our [Opensauce 2024](https://opensauce.com/) project "Voices in the Radio".

# clone/download this repo
if you are unfamiliar with git you can simply download and unzip this repo, or [check out this guide](https://github.com/git-guides) :)

# conda
## install conda
conda is a tool for python enviroment virtualization and management. it will handle our pypi python packages and libraries for us in whatever OS we like. you can use anaconda or miniconda. [follow the install instructions for your system](https://docs.anaconda.com/free/distro-or-miniconda/).

## create and activate a conda enviroment named **voices**
create an enviroment called voices using `conda create -n voices`

list your conda enviroments `conda info --envs`. the active enviroment is indicated with an asterisk(*).

enter the **voices** enviroment with `conda activate voices`

**Use `conda activate` to return to the base enviroment later when you are done working on this project.**

cd into the folder containing this repo. make sure you are in the folder containing requirements.txt and inside the **voices** conda enviroment, then run `pip install -r requirements.txt`

# docker
## install docker engine
docker provides provides a container with linux and python 3.10 installed, required libraries, and the setup for chromedriver. [follow the install guide for your OS detailed here](https://docs.docker.com/engine/install/)

verify docker's status by ensuring `docker info` returns client information

## docker configuration

build the docker container with `docker build -t voices .`

Mount local files to container and run bash on it with `docker run -it -p 4000:4000 -v $(pwd):/usr/src/app voices /bin/bash`

# create a .env file containing your api keys
create a file called `.env` to hold sensitive variable. Make sure this file is listed in your `.gitignore` file to ensure you aren't leaking your keys! **Make sure you do not list API keys, voice IDs, fine tuned model IDs, or any oth sensitive data in your .py scripts!! They should all be in `.env`!**
## Enter your OpenAI API key:
`OPENAI_API_KEY="API_KEY_GOES_HERE"`

## for TTS via [Eleven Labs](https://elevenlabs.io/), enter your API key and voice IDs.
`eleven_labs_api_key="ELEVEN_LABS_API_KEY_GOES_HERE"`
If you'd like to assign multiple models different voices, assign each voice ID with a differenent name to be selected from `.env` in the given model's python script.
`eleven_labs_voice1_id="ELEVEN_LABS_VOICE1_ID"`
`eleven_labs_voice2_id="ELEVEN_LABS_VOICE2_ID"`