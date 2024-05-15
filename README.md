# Voices-In-The-Radio-PUBLIC-
A system agnostic guide to fine tuning openai GPT models using conda and docker based on the workflow used in our Opensauce 2024 project "Voices in the Radio"

# Docker commands, for convenience
## What the Docker container provides
Some kind of Linux with Python 3.10 installed, required libraries, setup for Chromedriver.
## Build the Docker container
`docker build -t voices .`
## Mount local files to container and run bash on it
`docker run -it -p 4000:4000 -v $(pwd):/usr/src/app voices /bin/bash`
