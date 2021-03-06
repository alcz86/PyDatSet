# PyDatSet

Load various datasets in Python

## Description 

This repo contains pydatset, a package for loading (and eventually augmenting) datasets in python, you can check the source of each function into their pydocs. Currently supported datasets are:
 
 - [MNIST](http://yann.lecun.com/exdb/mnist/), [Kaggle MNIST](https://www.kaggle.com/c/digit-recognizer/)
 - [CIFAR-10](https://www.cs.toronto.edu/~kriz/cifar.html)
 - [Tiny-ImageNet](http://cs231n.stanford.edu/project.html) 
 - [GTSRB](http://benchmark.ini.rub.de/?section=gtsrb&subsection=news)
 - [SFDDD](https://www.kaggle.com/c/state-farm-distracted-driver-detection)

Pull requests are welcome!!!

## Requirements

- [numpy](www.numpy.org/)
- [scipy](www.scipy.org/) (used to load Tiny-ImageNet)
- [cv2](opencv.org/) (used to load GTSRB)
- [scikit-image](scikit-image.org/) (used for data augmentation)

## Installation

Get [pip](https://pypi.python.org/pypi/pip) and run:

	pip install git+git://github.com/dnlcrl/PyDatSet.git
	

## Usage

Download the required dataset (e.g. cifar10 ) and call the respective `load(path)` function, for example:

	$ python
	>>> from pydatset import cifar10
	>>> data = cifar10.load('path/to/cifaf10')

Apply data augmentation to a given batch by doing something like:

	>>> from pydatset.data_augmentation import (random_contrast, random_flips,
	...                                          random_crops, random_rotate,
	...                                          random_tint)
	>>> batch = random_tint(batch)
	>>> batch = random_contrast(batch)
	>>> batch = random_flips(batch)
	>>> batch = random_rotate(batch, 10)
	>>> batch = random_crops(batch, (32, 32), pad=2)
	

check pydatset/README.md for more infos about the package contents.
