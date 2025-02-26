# FlowFuser

In the following we will explain out to use this repository.

## Download Carla 0.9.15
Download Carla 0.9.15 Nightly Build from [here](https://github.com/carla-simulator/carla/blob/master/Docs/download.md).

You can try if Carla is working with the following command:

    ./<carla_folder>/CarlaUE4.sh

## Get This Repo and Python Setup

    git clone https://github.com/Noce99/FlowFuser.git

    cd FlowFuser

    python3.7 -m venv ./

    source bin/activate

    pip install -r requirements.txt

## Generate a Dataset
    
    python 1_dataset_creation.py --carla_path <carla_folder>

You will find the dataset folder in the _datasets_ folder.
After having created enough dataset folders:

    cd datasets
    
    mkdir train_dataset

    cp ./* train_dataset

## Training

1. Backbone Training


    python 2_train.py --just_backbone --use_bev_semantic --use_depth

2. Full Network Training


    python 2_train.py --use_bev_semantic --use_depth --weights_path <path_to_model_****.pth>

