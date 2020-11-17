#Autonomous Vehicle Project 2020

## General Information
My personal repository contains what I'm learning through this course [Autonomous Vehicles Project Autumn 2020](https://courses.cs.ut.ee/2020/AutVehProj/fall/Main/Track-ADL) from the University of Tartu

## Software Stack
- Baidu Apollo v5.5+ (`git clone` from [here](https://github.com/ApolloAuto/apollo))
- LGSVL Simulator (documentation from [here](https://www.lgsvlsimulator.com/docs/))
- Docker Engine (documentation from [here](https://docs.docker.com/engine/install/ubuntu/))

## Prerequisites
- Ubuntu 16.04 or later (Ubuntu 18.04 is preferred)
- Nvidia graphics card (required for Perception)
 - Nvidia proprietary driver (>=410.48) must be installed
- Docker 19.03+

## Installation
Following tutorial from [Apollo github page](https://github.com/ApolloAuto/apollo/blob/master/docs/specs/prerequisite_software_installation_guide.md)

### NVIDIA GPU Driver
```
sudo apt-get update
sudo apt-add-repository multiverse
sudo apt-get update
sudo apt-get install nvidia-driver-440
```
Type `nvidia=smi` to check if NVIDIA GPU works fine

### Docker Engine
- Apollo 6.0+ requires Docker 19.03+ to work properly
- Follow this [tutorial](https://docs.docker.com/engine/install/ubuntu/)

### NVIDIA Container Toolkit
```
distribution=$(. /etc/os-release;echo $ID$VERSION_ID)
curl -s -L https://nvidia.github.io/nvidia-docker/gpgkey | sudo apt-key add -
curl -s -L https://nvidia.github.io/nvidia-docker/$distribution/nvidia-docker.list | sudo tee /etc/apt/sources.list.d/nvidia-docker.list
sudo apt-get -y update
sudo apt-get install -y nvidia-container-toolkit
```
Restart Docker daemon for the changes above to take effect.
`sudo systemctl restart docker`

## Apollo Setup
- clone the repository `git clone https://github.com/ApolloAuto/apollo`
- launch the container and mount a few volumes `./docker/scripts/dev_start.sh`
- enter the container `./docker/scripts/dev_into.sh`
- build apollo `./apollo.sh build_opt_gpu` (optimized, not debug, with GPU support)

**NOTE** The Apollo build may fail on machines with less than 1GB of RAM per CPU core due to aggressive parallelization in the build, as discussed in [Apollo issue 7719](https://github.com/ApolloAuto/apollo/issues/7719).


## Running Apollo via LGSVL Simulator
- enter the container from Apollo root folder `./docker/scripts/dev_into.sh`
- activate dreamview `./scripts/bootstrap_lgsvl.sh`
- activate the bridge `./scripts/bridge.sh`
- more instructions from [here](https://www.lgsvlsimulator.com/docs/apollo-master-instructions/)

### Sample Demonstration Video
- Watch [Running Baidu Apollo via LGSVL Simulator](https://youtu.be/adaWOz_d0tM)
