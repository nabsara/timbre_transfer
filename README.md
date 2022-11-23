# ML Project: Timbre transfer


## Train your model

1. Open a screen session:
```bash
$ screen -S "name"  # to create a new screen

$ screen -r "name"  # to rattach if screen already exists
```
NB : To exit a screen but not delete it do : ctrl + A and then ctrl + D (To delete a screen just do ctrl + D)

2. activate your Python virtual environment. If you use miniconda just do:

```bash
path/to/timbre_transfer$ source ../miniconda/bin/activate  # change absolute path if needed
```
NB : do not forget to install the dependencies the first time with:
```bash
(base) path/to/timbre_transfer$ pip install -r requirements.txt
```

3. Export environment variables and specify the GPU to use:
```bash
(base) path/to/timbre_transfer$ export PYTHONPATH=$PYTHONPATH:${PWD}/src
(base) path/to/timbre_transfer$ export CUDA_VISIBLE_DEVICES=1  # replace the value with the GPU id you want to use
```
NB: Check the available GPU with `$ nvidia-smi`

4. Set the training config:
- copy the template config:
```bash
(base) path/to/timbre_transfer$ cp ./config/config_vae_template.yaml ./config/config_vae_mnist.yaml
```
- Modify the config via your IDE if you have the remote-ssh vscode extension or directly in the terminal:
```bash
(base) path/to/timbre_transfer$ vi ./config/config_vae_mnist.yaml
```
NB: Do not foget to save! 

5. Launch training:
```bash
(base) path/to/timbre_transfer$ python -m timbre_transfer train ./config/config_vae_mnist.yaml
```