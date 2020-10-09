#Start from an image that suit your device
FROM nvidia/cuda:10.1-cudnn7-devel-ubuntu18.04


RUN echo "deb http://archive.ubuntu.com/ubuntu trusty-backports main restricted universe multiverse" >> /etc/apt/sources.list 

RUN apt-get update && \
    apt-get install -y build-essential \
                        apt-utils \
                        python-dev \
                        python3.8 \
                        python-pip \
                        python3-pip \
                        python-opengl \
                        ffmpeg \
                        graphviz \
                        xvfb \ 
                        cmake \
                        swig3.0 && \
                        ln -s /usr/bin/swig3.0 /usr/bin/swig

RUN apt-get upgrade -y

RUN pip install --upgrade pip

# Deep learning
RUN pip3 install --upgrade numpy \
                scipy \ 
                pandas \ 
                sklearn \
                jupyter \ 
                matplotlib \
                gym \ 
                pyglet \
                tqdm \
                graphviz \
                pydot \
                pydot_ng \ 
                seaborn \
                scikit-image \
                tensorflow-gpu==2.1 
                


RUN python3 -m ipykernel.kernelspec


EXPOSE 8888
VOLUME /notebooks
WORKDIR /notebooks

CMD ["jupyter", "notebook", "--port=8888", "--no-browser", "--ip=0.0.0.0", "--allow-root"]