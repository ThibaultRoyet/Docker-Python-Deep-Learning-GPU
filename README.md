# Docker Python Deep Learning GPU


<p float="left">
  <img src="images/docker_logo.png" width="150" />
  <img src="images/nvidia_logo.png" width="150" /> 
  <img src="images/python_logo.png" width="150" />
  <img src="images/scikit_learn_logo.png" width="150" />
  <img src="images/tensorflow_logo.png" width="150" />
</p>

This is a docker image for deep learning that I created in march 2020.
The docker can use nvidia GPU therefore the docker image is quite big (6GB+).
You can check https://hub.docker.com/r/nvidia/cuda/ if you want to switch the based image but make sure that its compatible with the tensorflow version.

Using docker-compose you can avoid the very long command line to start your container and its easy to modify!
Don't hesitate to add a ton of library like Pytorch, OpenCV, The dockerfile is very short and easy to modify on purpose! :)

Finaly you might want to check the docker-compose.yml for different purposes:
- If you want or don't want to use your nvidia GPU, check the runtime section
- If you want to add a shared volume (between you conputer and the container, Very usefull!)
- If you want to have a fixed value for you jupyter token that you need everytime you start the jupyter

## Included Libraries
* Ubuntu 18.04 LTS
* CUDA 10.1
* Python 3.8
* Tensorflow 2.1
* Jupyter Notebook
* Numpy, Scikit Learn, Scikit Image, Pandas, Matplotlib


## Getting Started

### Prerequisites

You will need to have installed:
* Docker:
https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository
* Docker-compose:
https://docs.docker.com/compose/install/
* nvidia-docker:
https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html#docker



### Installing

You just need to clone the repo.

```
git clone git@github.com:ThibaultRoyet/Docker-Python-Deep-Learning-GPU.git
cd Docker-Python-Deep-Learning-GPU
docker-compose build
```

### Running

Go in the folder and start the container
```
docker-compose up
```

After you start the container you can access to jupyter that as been automaticly start on this address:
http://localhost:18888/

And you can acces to the terminal container using your terminal with the following command line.
```
docker-compose exec notebook bash
```


## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details


## Issues

### Common issues 

GPU Runtime problems:
https://github.com/docker/compose/issues/6691
https://stackoverflow.com/questions/59222651/error-the-compose-file-docker-compose-yaml-is-invalid-because-unsupported

root permissions:
https://stackoverflow.com/questions/48957195/how-to-fix-docker-got-permission-denied-issue


## Usefull link

Hardware compatibilty: https://www.tensorflow.org/install/gpu?hl=fr#hardware_requirements

Cuda image: https://hub.docker.com/r/nvidia/cuda/

