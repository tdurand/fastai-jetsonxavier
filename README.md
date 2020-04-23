# How to setup fastai course on Jetson Xavier

Fast.ai course: https://course.fast.ai/

Based on: https://github.com/brtknr/fastai-jetson-nano

## apt-get dependencies

```bash
sudo apt-get -y update
sudo apt-get -y upgrade
sudo apt-get -y purge \
	python3-numpy python3-scipy \
	python3-matplotlib python3-pandas python3-pil

sudo apt-get -y install \
	python3-pip build-essential python-dev git \
	cython python-requests python-typing \
	g++ cmake python-dev \
	nodejs npm freetype2-demos \
	zlib1g-dev zip libjpeg8-dev libhdf5-dev \
	libhdf5-serial-dev hdf5-tools \
	pkg-config libfreetype6-dev libpng-dev \
	libblas3 liblapack3 liblapack-dev libblas-dev \
	gfortran htop

```

## pip dependencies

download requirements.txt file from this repo: https://github.com/tdurand/fastai-jetsonxavier/blob/master/requirements.txt

```bash

pip3 install -r requirements.txt

```

## pytorch

Links for wheel files: https://github.com/pytorch/pytorch#nvidia-jetson-platforms

Go to the link and get the latest .whl file

```bash
pip3 install torch-1.4.0-cp36-cp36m-linux_aarch64.whl
```

## torchvision

reference guide: https://forums.developer.nvidia.com/t/pytorch-for-jetson-nano-version-1-4-0-now-available

```bash
sudo apt-get install libjpeg-dev zlib1g-dev
git clone --branch v0.5.0 https://github.com/pytorch/vision torchvision
cd torchvision
python3 setup.py install
```

## fastai

```bash
pip3 install fastai --no-deps
```

jupyter notebook

```bash
echo "done with part1 - now logout, login again and run setup_jupyter.sh"
jupyter labextension install @jupyter-widgets/jupyterlab-manager
jupyter labextension install @jupyterlab/statusbar
jupyter lab --generate-config
cp jupyter_notebook_config.py .jupyter/jupyter_notebook_config.py
jupyter notebook password
```

```bash
git clone https://github.com/fastai/course-v3.git
cd course-v3
jupyter notebook
```


## Common errors

if you get, couldn't find this dependency, just restart the terminal and type the command again
