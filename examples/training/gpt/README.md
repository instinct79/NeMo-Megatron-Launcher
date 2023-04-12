### GPT Pretraining example scripts
These scripts run a recommended config for GPT pretraining, for 5b and 20b model sizes on a single 8-gpu node

- [a100](https://github.com/NVIDIA/NeMo-Megatron-Launcher/tree/example_run_scripts/examples/training/gpt/a100)
: Scripts to run GPT pretraining on NVIDIA A100, in bf16 type

- [h100](https://github.com/NVIDIA/NeMo-Megatron-Launcher/tree/example_run_scripts/examples/training/gpt/h100)
: Scripts to run GPT pretraining for NVIDIA H100, in fp8 type

#### Setup
1. Update the following bash variables in the example run scripts:
     - ``` NEMO_MEGATRON_LAUNCHER_DIR ``` : the directory of where this repository is located

     - ``` DATA_DIR ``` : the directory of the dataset used for pretraining, by default this is ``` NEMO_MEGATRON_LAUNCHER_DIR/data ```

2. Enter your cluster enviroment settings at 
  [config.yaml](https://github.com/NVIDIA/NeMo-Megatron-Launcher/blob/master/launcher_scripts/conf/config.yaml)
    
    For bcm type clusters update the job name, partition, and account at [bcm.yaml]( https://github.com/NVIDIA/NeMo-Megatron-Launcher/blob/master/launcher_scripts/conf/cluster/bcm.yaml)
    
For further details see [5.3.2.1 General Configuration](https://github.com/NVIDIA/NeMo-Megatron-Launcher#5321-general-configuration) 

#### Results
Results are by default stored at ``` NEMO_MEGATRON_LAUNCHER_DIR/results/<experiment_name> ``` with the following structure:

- ``` NEMO_MEGATRON_LAUNCHER_DIR/results/<experiment_name>/<experiment_name>.yaml ``` : The config of the pretrained model
- ``` NEMO_MEGATRON_LAUNCHER_DIR/results/<experiment_name>/<jobname>_<experiment_name>.sh ``` : The autogenerated .sh file that was run
- ``` NEMO_MEGATRON_LAUNCHER_DIR/results/<experiment_name>/results/ ``` : Directory contained per rank logs, and tensorboard data.

For further details see [5.3.2.4 General Configuration](https://github.com/NVIDIA/NeMo-Megatron-Launcher#5324-interpreting-the-results) 





  