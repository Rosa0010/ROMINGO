# ROMINGO
Class Project (57000)

This Repo contains Jupyter Notebook (python) on the implementation of Romingo, a Visual Language model for few-shot learning and a video demonstration of the key features and evaluation results. This is a reimplementation of DeepMind’s Flamingo model (https://arxiv.org/pdf/2204.14198)

## Video Demo
To watch the video demonstration, download the “demo” video file.

## Datasets and Pre-trained Weights
With the exception of the COCO dataset train and val images (which are downloaded in the code from Kaggle), access to all other datasets and model pre-trained weights have been provided to the Professors via email. Access is a link to my google drive space to obtain the needed files. Professors will distribute access as needed. 

## Code
Ideally, you should run this code in Google Colab. It needs just one GPU, hence distributed training is not required, although options (code) for it are provided.
The code does three major things: TRAIN, INFERENCE, and EVALUATION. The code is well-commented so you know the point of the notebook you are in. 

Setup – Download the romingo_train_inf_eval.ipynb and open it in Google Colab (or any other Jupyter environment).

Before you run any part of the code (train, inference, evaluation), you need to run all the blocks before the “The Main Training” block (1-13). Training, Inference and Evaluation are dependent on the contents in the blocks from 1 to 13.

All the needed packages to run the code are defined in the first block with a “pip install”, run that cell to download the packages (block 1). A requirements.txt file is also provided. You can simply pip install the requirements.txt file every time you start a runtime (save it locally in your colab instance directory to do this).

### Train
There are some paths and variables to set before running the training script.
* __wandb (block 2)__ - This is optional for monitoring weights in wandb. I used it to keep track of training checkpoints, execution time, losses, and other system resources. To use this, create a wandb account and provide the API key (gotten from the wandb site) when prompted at login. You can avoid use by not running this block and setting its parameters to false in the Training blocks (both for Romingo and Romingo-fewer).
* __mount drive (block 3)__ - I mounted my Google Drive to be able to access my datasets and checkpoint weights. If you are running on colab or using paths in your drive, you should mount the drive. If there is no drive to mount, you can skip running this cell
* __os env. variables (block 12)__ - The default is already in the code. This may or may not need to be changed
* __main training (block 14)__ - In the main training block, at lines 80 and 80, you need to change the path to the LAION and MMC4 datasets to match where you have them stored. It should be in the form  __/path/to/laion_or_mmc4/{00000..00048}.tar__. Remember to also set parameters for wandb to False if not using it. If you are, then fill all the args for wandb

To run the training for the fewer model Flamingo (block 15) after making the needed changes just like was done in block 14, you have to restart the runtime, run all the blocks from 1-13 (2 and 3 are optional) and do so. 

### Inference
This part starts from block 16 and ends right before the Evaluation block (17).

* Run the codes from blocks 1-13 (2 and 3 are dependent on whether you are using wandb and Google Drive)
* Set the path to your saved model checkpoint in the immediate cell for inference, there is a comment in the code to show you where (this should be the last checkpoint which represents the final model after 50 epochs)
* A link to the folder containing the inference images will be shared with the professors. Get the folder with the images and set the path to those images in the Inference 1, 2 and 3 blocks to get the reported results. The images in the inference folder are names just are they appear on the code, hence you can easily map the images.

### Evaluation
This is the last part of the code and starts from the labeled Block 17.

* Run the codes from blocks 1 to 13 (2 and 3 needed where applicable)
* Before running the eval code, there are a few changes to make, in cells labeled __17.1 and 17.2__. Set the "coco dataset" arguments. The train_img and val_img paths should remain unchanged since they are downloaded from Kaggle, but the paths to the kaparthy and annotations JSON files should be set. Set the path to where the model weights (checkpoint) can be found. The links to these files have been given to the professors. 
* Run every cell from 17 to the cell labeled 17.1 (17.1 should be run once you have set the eval paths and are ready to evaluate the main Flamingo model)
* Run 17.2 if you are ready to evaluate for the Romingo-fewer model. Just like in training, you have to restart the training runtime before you can run this (if you just run 17.1 in the same runtime it will not work - you will run into an error).
* The code block after 17.2 simply plots the graph of model accuracies between Romingo and Romingo-fewer. 

