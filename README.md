# ROMINGO
Class Project (57000)

This Repo contains Jupyter Notebook (python) on the implementation of Romingo, a Visual Language model for few-shot learning and a video demonstration of the key features and evaluation results. This is a reimplementation of DeepMind’s Flamingo model (https://arxiv.org/pdf/2204.14198)

## Video Demo
To watch the video demonstration, download the “demo” file.

## Code
Ideally, you should run this code in Google Colab. It needs just one GPU, hence distributed training is not defined, although options (code) for it is provided.
The code does three major things: TRAIN, INFERENCE and EVALUATION. The code is well commented so you know the point of the notebook you are in. 

Setup – Download the romingo_train_inf_eval.ipynb and open in google colab (or any other Jupyter enviroment).

Before you run any part of the code (train, inference, evaluation), you need to run all the blocks before the “The Main Training” block (1-13). Training, Inference and Evaluation are dependent on the contents in the blocks from 1 to 13.

All the needed packages to run the code are defined in the first block with a “pip install”, run that cell to download the packages (block 1). A requirements.txt file is also provided. You can simply pip install the requirements.txt file every time you start a runtime (save it locally in your colab instance directory to do this).

### Train
There are a number of paths and variables to set prior to running the train script.
* __wandb (block 2)__ - This is optional for monitoring weights in wandb. I used it to keep track of training checkpoints, execution time, losses and other system resources. To use this, create a wandb account and provide the API key (gotten from the wandb site) when prompted at login. You can avoid use by not running this block and setting its parameters to false in the Training blocks (both for Romingo and Romingo-fewer).
* __mount drive (block 3)__ - I mounted my google drive to be able to access my datasets and checkpoint weights. If you are running on colab or using paths in your drive, you should mount the drive. If there is no drive to mount, you can skip running this cell
* __os env. variables (block 12)__ - The default is already in the code. This may or may not need to be changed
* __main training (block 14)__ - In the main training block, at lines 80 and 80, you need to change the path to the LAION and MMC4 datasets to match where you have them stored. It should be in the form  __/path/to/laion_or_mmc4/{00000..00048}.tar__. Remember to also set paramters for wandb to False if not using it. If you are, then fill all the args for wandb

To run the training for the fewer model Flamingo (block 15), you have to restart the runtime, run all the blocks from 1-13 (2 and 3 are optional) and do so. 
