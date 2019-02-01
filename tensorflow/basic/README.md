
* Tensorflow basic
  * [Session](201_session.py)
  * [Placeholder](202_placeholder.py)
  * [Variable](203_variable.py)
  * [Activation](204_activation.py)
* Build your first network
  * [Regression](301_simple_regression.py)
  * [Classification](302_simple_classification.py)
  * [Save and reload](303_save_reload.py)
  * [Optimizers](304_optimizer.py)
  * [Tensorboard](305_tensorboard.py)
  * [Dataset](306_dataset.py)
* Advanced neural network
  * [CNN](401_CNN.py)
  * [RNN-Classification](402_RNN_classification.py)
  * [RNN-Regression](403_RNN_regression.py)
  * [AutoEncoder](404_AutoEncoder.py)
  * [DQN Reinforcement Learning](405_DQN_reinforcement_learning.py)
  * [GAN (Generative Adversarial Nets)](406_GAN.py) / [Conditional GAN](406_conditional_GAN.py)
  * [Transfer Learning](407_transfer_learning.py)
* Others (WIP)
  * [Dropout](501_dropout.py)
  * [Batch Normalization](502_batch_normalization.py)
  * [Visualize Gradient Descent](503_visualize_gradient_descent.py)
  * [Distributed training](504_distributed_training.py)

# install

### 1 clone tensorflow from github
$ git clone https://github.com/tensorflow/tensorflow

$ cd tensorflow
$ git checkout {{Branch}} ### where Branch is the desired branch, maybe "master"

### 2 install bazel: https://bazel.build/versions/master/docs/install.html
### better to update bazel, lower version does not work

### 3 mac install these
$ sudo pip install six numpy wheel

### 3 linux install these
$ sudo apt-get install python3-numpy python3-dev python3-pip python3-wheel

### 4 direct to tensorflow and configure files
$ cd tensorflow  ### cd to the top-level directory created
### found out where is your python program for configure
$ ./configure

### 5 build wheel
$ bazel build -c opt --copt=-mavx --copt=-mavx2 --copt=-mfma --copt=-mfpmath=both --copt=-msse4.2 //tensorflow/tools/pip_package:build_pip_package
$ bazel-bin/tensorflow/tools/pip_package/build_pip_package /tmp/tensorflow_pkg

### 6 install pip
$ sudo pip3 install /tmp/tensorflow_pkg/tensorflow-{{your version}}.whl
