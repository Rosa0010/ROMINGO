# ROMINGO
Class Project (57000)

This Repo contains Jupyter Notebook (python) on the implementation of Romingo, a Visual Language model for few-shot learning and a video demonstration of the key features and evaluation results. This is a reimplementation of DeepMind’s Flamingo model (https://arxiv.org/pdf/2204.14198)

##Video Demo
To watch the video demonstration, download the “demo” file.

##Code
Ideally, you should run this code in Google Colab. 
The code does three major things: TRAIN, INFERENCE and EVALUATION. The code is well commented so you know the point of the notebook you are in. 

Setup – Download the romingo_train_inf_eval.ipynb and open in google colab (or any other Jupyter enviroment).

Before you run any part of the code (train, inference, evaluation), you need to run all the blocks before the “The Main Training” block (1-13). Training, Inference and Evaluation are dependent on the contents in the blocks from 1 to 13.

All the needed packages to run the code are defined in the first block with a “pip install”, run that cell to download the packages (block 1). A requirements.txt file is also provided. You can simply pip install the requirements.txt file every time you start a runtime (save it locally in your colab instance directory to do this).

