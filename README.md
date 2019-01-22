# Template code for the genre classification project of ENSEA course "Electronique et Signal Musical".

## Setup
The easiest way to run the provided code is to build the provided Dockerfile using Docker. The provided image contains all 
First, you need to install [Docker](https://docs.docker.com/install/).
Then clone this project:
```sh
git clone https://github.com/romi1502/genre_classification_ensea_project.git
```
Then change to the directory of the repo and build the image :
```sh
cd genre_classification_ensea_project
docker build -t genre_classification_image docker
```
It may take a while since it will download the small version of the [FMA dataset](https://github.com/mdeff/fma#data) (about 8GB).

Once the image is built you can launch a container in interactive mode using:
```sh
docker run -ti --rm --name genre_classification_container genre_classification_image
```
Once in the container, you should be able to run the basic provided training script `train_model.py` like this:
```sh
python train_model.py
```
All used data and dependencies are self contained in the docker image.

## Docker tips

If you want to edit code in your favorite code editor and make accessible within the docker container, you can mount a path of your computer filesystem within the docker filesystem when launching your container using the `-v`option:
```sh
docker run -ti --rm --name genre_classification_container -v /my/local/path/:/path/in/docker/container genre_classification_image
```
Then you should be able to access files located on your computer at `/my/local/path/` within the container at path `/path/in/docker/container`


You can let run a script within your docker container and check it afterwards:
* you can detach from your docker container using the keyboard combination: 'Ctrl'+'P', 'Ctrl'+'Q'
* you can attach back to your running docker container with the command:
```sh
docker attach genre_classification_container
```
