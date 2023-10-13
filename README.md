# LiuBoss.Docker
[![Awesome](https://awesome.re/badge-flat.svg)](https://liuboss1992.github.io/)

Dockerfile and Dockerimg by Boss Liu.

---
### Jump to

1. [Images Dependencies](#jump1)
2. [Details](#jump2)
    1. [liucb-py36-cuda90-base](#jump2.1)
    2. [liucb-py36-cuda90-pycore](#jump2.2)
    3. [liucb-py36-cuda90-torch041](#jump2.3)
    4. [liucb-py38-cuda111-torch1101-conda](#jump2.4)

---
To do

* [] conda

---
## Images Dependencies <span id="jump1">
```
｜--liucb-py36-cuda90-base 
    ｜--liucb-py36-cuda90-pycore
       ｜--liucb-py36-cuda90-torch041
```

----

## Details <span id="jump2">

### [liucb-py36-cuda90-base](https://github.com/liuboss1992/LiuBoss.Docker/tree/master/liucb-py36-cuda90-base)<span id="jump2.1">

Basic environment. Based on **nvidia/cuda:9.2-cudnn7-devel-ubuntu16.04**, add debian application for caffe compiler, and update python to version **Python 3.6.11**.

#### how to use
```
docker pull liuboss/pami:liucb-py36-cuda90-base
```

#### pip list

```
root@b269a03b5e32:/# pip list
Package    Version
---------- ----------------------
pip        20.1.1
pycurl     7.43.0
pygobject  3.20.0
python-apt 1.1.0b1+ubuntu0.16.4.9
setuptools 20.7.0
wheel      0.29.0
```

### [liucb-py36-cuda90-pycore](https://github.com/liuboss1992/LiuBoss.Docker/tree/master/liucb-py36-cuda90-pycore) <span id="jump2.2">

Based on **liucb-py36-cuda90-base**, install core python packages except the deep learning tools.

#### how to use
```
docker pull liuboss/pami:liucb-py36-cuda90-pycore
```

#### pip list

```
root@2e2ab24784d2:/# pip list
Package             Version
------------------- ----------------------
appdirs             1.4.4
attrs               19.3.0
backcall            0.2.0
bleach              3.1.5
certifi             2020.6.20
cffi                1.14.0
chardet             3.0.4
cycler              0.10.0
Cython              0.29.20
DateTime            4.3
decorator           4.4.2
deepdish            0.3.6
defusedxml          0.6.0
distlib             0.3.1
dlib                19.17.0
dominate            2.5.1
easydict            1.9
entrypoints         0.3
fasteners           0.15
filelock            3.0.12
fire                0.3.1
fjcommon            0.2.12
future              0.18.2
h5py                2.10.0
hypertools          0.6.2
idna                2.10
imageio             2.8.0
importlib-metadata  1.7.0
importlib-resources 3.0.0
ipdb                0.13.3
ipykernel           5.3.0
ipython             7.16.1
ipython-genutils    0.2.0
ipywidgets          7.5.1
jedi                0.17.1
Jinja2              2.11.2
joblib              0.16.0
json5               0.9.5
jsonpatch           1.26
jsonpointer         2.0
jsonschema          3.2.0
jupyter             1.0.0
jupyter-client      6.1.5
jupyter-console     6.1.0
jupyter-core        4.6.3
jupyterlab          2.1.5
jupyterlab-server   1.1.5
kiwisolver          1.2.0
leveldb             0.201
llvmlite            0.33.0
lmdb                0.98
MarkupSafe          1.1.1
matplotlib          3.2.2
mistune             0.8.4
monotonic           1.5
nbconvert           5.6.1
nbformat            5.0.7
networkx            2.4
nose                1.3.7
notebook            6.0.3
numba               0.50.1
numexpr             2.7.1
numpy               1.19.0
opencv-python       4.2.0.34
packaging           20.4
pandas              1.0.5
pandocfilters       1.4.2
parso               0.7.0
pexpect             4.8.0
pickleshare         0.7.5
Pillow              7.2.0
pip                 20.1.1
ppca                0.0.4
prometheus-client   0.8.0
prompt-toolkit      3.0.5
protobuf            3.12.2
ptyprocess          0.6.0
pycparser           2.20
pycurl              7.43.0
pydicom             2.0.0
Pygments            2.6.1
pygobject           3.20.0
pyparsing           2.4.7
pyrsistent          0.16.0
python-apt          1.1.0b1+ubuntu0.16.4.9
python-dateutil     2.8.1
python-gflags       3.1.2
pytz                2020.1
PyWavelets          1.1.1
PyYAML              5.3.1
pyzmq               19.0.1
qtconsole           4.7.5
QtPy                1.9.0
requests            2.24.0
scikit-image        0.17.2
scikit-learn        0.23.1
scikit-video        1.1.11
scipy               1.5.0
seaborn             0.10.1
Send2Trash          1.5.0
setuptools          47.3.1
SimpleITK           1.2.4
six                 1.15.0
sklearn             0.0
tables              3.6.1
termcolor           1.1.0
terminado           0.8.3
testpath            0.4.4
threadpoolctl       2.1.0
tifffile            2020.6.3
torchfile           0.1.0
tornado             6.0.4
tqdm                4.47.0
traitlets           4.3.3
urllib3             1.25.9
virtualenv          20.0.25
visdom              0.1.8.9
wcwidth             0.2.5
webencodings        0.5.1
websocket-client    0.57.0
wheel               0.29.0
widgetsnbextension  3.5.1
zipp                3.1.0
zope.interface      5.1.0
```

### [liucb-py36-cuda90-torch041](https://github.com/liuboss1992/LiuBoss.Docker/tree/master/liucb-py36-cuda90-torch041) <span id="jump2.3">

Based on **liucb-py36-cuda90-pycore**, install deep learning tools with tensorflow-gpu=1.14.0, tensorboard=1.14.0, tensorboardX=1.8 torch=0.4.1 and torchvision=0.2.1.

#### how to use
```
docker pull liuboss/pami:liucb-py36-cuda90-torch041
```

#### pip list

```
root@2dc8d34143e7:/# pip list
Package              Version
-------------------- ----------------------
absl-py              0.9.0
appdirs              1.4.4
astor                0.8.1
attrs                19.3.0
backcall             0.2.0
bleach               3.1.5
certifi              2020.6.20
cffi                 1.14.0
chardet              3.0.4
cycler               0.10.0
Cython               0.29.20
DateTime             4.3
decorator            4.4.2
deepdish             0.3.6
defusedxml           0.6.0
distlib              0.3.1
dlib                 19.17.0
dominate             2.5.1
easydict             1.9
entrypoints          0.3
fasteners            0.15
filelock             3.0.12
fire                 0.3.1
fjcommon             0.2.12
future               0.18.2
gast                 0.3.3
google-pasta         0.2.0
grpcio               1.30.0
h5py                 2.10.0
hypertools           0.6.2
idna                 2.10
imageio              2.8.0
importlib-metadata   1.7.0
importlib-resources  3.0.0
ipdb                 0.13.3
ipykernel            5.3.0
ipython              7.16.1
ipython-genutils     0.2.0
ipywidgets           7.5.1
jedi                 0.17.1
Jinja2               2.11.2
joblib               0.16.0
json5                0.9.5
jsonpatch            1.26
jsonpointer          2.0
jsonschema           3.2.0
jupyter              1.0.0
jupyter-client       6.1.5
jupyter-console      6.1.0
jupyter-core         4.6.3
jupyterlab           2.1.5
jupyterlab-server    1.1.5
Keras-Applications   1.0.8
Keras-Preprocessing  1.1.2
kiwisolver           1.2.0
leveldb              0.201
llvmlite             0.33.0
lmdb                 0.98
Markdown             3.2.2
MarkupSafe           1.1.1
matplotlib           3.2.2
mistune              0.8.4
monotonic            1.5
nbconvert            5.6.1
nbformat             5.0.7
networkx             2.4
nose                 1.3.7
notebook             6.0.3
numba                0.50.1
numexpr              2.7.1
numpy                1.19.0
opencv-python        4.2.0.34
packaging            20.4
pandas               1.0.5
pandocfilters        1.4.2
parso                0.7.0
pexpect              4.8.0
pickleshare          0.7.5
Pillow               7.2.0
pip                  20.1.1
ppca                 0.0.4
prometheus-client    0.8.0
prompt-toolkit       3.0.5
protobuf             3.12.2
ptyprocess           0.6.0
pycparser            2.20
pycurl               7.43.0
pydicom              2.0.0
Pygments             2.6.1
pygobject            3.20.0
pyparsing            2.4.7
pyrsistent           0.16.0
python-apt           1.1.0b1+ubuntu0.16.4.9
python-dateutil      2.8.1
python-gflags        3.1.2
pytz                 2020.1
PyWavelets           1.1.1
PyYAML               5.3.1
pyzmq                19.0.1
qtconsole            4.7.5
QtPy                 1.9.0
requests             2.24.0
scikit-image         0.17.2
scikit-learn         0.23.1
scikit-video         1.1.11
scipy                1.5.0
seaborn              0.10.1
Send2Trash           1.5.0
setuptools           47.3.1
SimpleITK            1.2.4
six                  1.15.0
sklearn              0.0
tables               3.6.1
tensorboard          1.14.0
tensorboardX         1.8
tensorflow-estimator 1.14.0
tensorflow-gpu       1.14.0
termcolor            1.1.0
terminado            0.8.3
testpath             0.4.4
threadpoolctl        2.1.0
tifffile             2020.6.3
torch                0.4.1
torchfile            0.1.0
torchvision          0.2.1
tornado              6.0.4
tqdm                 4.47.0
traitlets            4.3.3
urllib3              1.25.9
virtualenv           20.0.25
visdom               0.1.8.9
wcwidth              0.2.5
webencodings         0.5.1
websocket-client     0.57.0
Werkzeug             1.0.1
wheel                0.29.0
widgetsnbextension   3.5.1
wrapt                1.12.1
zipp                 3.1.0
zope.interface       5.1.0
```
### [liucb-py38-cuda111-torch1101-conda](https://github.com/liuboss1992/LiuBoss.Docker/tree/master/liucb-py38-cuda111-torch1101-conda) <span id="jump2.4">

#### Core features
```
# ubuntu 20.04
# python        3.8     
# pytorch       1.10.1
# torchvision   0.11.2
# conda         py311_23.5.2
```
#### how to use
```
docker pull liuboss/pami:liucb-py38-cuda111-torch1101-conda
```
#### pip list

