# Template code for the genre classification project of ENSEA course "Electronique et Signal Musical".

## Setup
The easiest way to run the provided code is to build the provided Dockerfile using Docker. 
First, you need to install [Docker](https://docs.docker.com/install/).
Then clone this project:
```sh
git clone https://github.com/romi1502/genre_classification_ensea_project.git
```
Then change dire to the directory of the repo and build the image :
```sh
cd genre_classification_ensea_project
docker build -t genre_classification_image docker
```
It may take a while since it will download all the small version of the [FMA dataset](https://github.com/mdeff/fma#data) (about 8GB).

Once the image is built you can launch a container in interactive mode using:
```sh
docker run -ti --rm --name genre_classificaiton_container genre_classification_image
```
Once in the container, you should be able to run the basic provided training script `train_model.py` like this:
```sh
python train_model.py
```