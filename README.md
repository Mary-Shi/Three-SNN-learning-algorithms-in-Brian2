# Single-layer-SNN-simulation-in-Brian
The repository offer the simulation scripts for three single-layer SNN learning algorihtms with different homeostasis method proposed by Querlioz [1], Diehl [2] and the author of this repository. The neural models used in simulation are all the same with the models introduced in [1].

>[1]: Querlioz D, Bichler O, Dollfus P, et al. Immunity to Device Variations in a Spiking Neural Network With Memristive Nanodevices[J]. IEEE Transactions on Nanotechnology, 2013, 12(3): 288-295.

>[2]: Diehl P U, Cook M. Unsupervised learning of digit recognition using spike-timing-dependent plasticity.[J]. Frontiers in Computational Neuroscience, 2015: 99-99.
## Simulation environment
The modules needed to be installed in **Python 2.7** are as follows:
*********************
- Brian2 2.2.1
- Cython 0.29
- matplotlib 2.2.3
- mpmath 1.1.0
- nose 1.3.7
- numpy 1.16.3 pip 19.1
- pyparsing 2.4.0
- pytz 2019.1 
- setuptools 41.0.1 
- six 1.12.0 
- subprocess32 3.5.3
- sympy 1.3
- wheel 0.33.1
*******************
## source file description in SNN simulation
- talent_run.sh : the top-level bash shell for runnning the simulation, data processing and classifying.
- Oneinhi_Querlioz.py : the Brian2 simulation script of single-layer fully-connected SNN reproduced from the SNN learning algorithm proposed by Querlioz.
- Oneinhi_Diehl.py : the Brian2 simulation script of single-layer fully-connected SNN using the homeostasis method proposed by Diehl.
- Oneinhi_MemristorLeaky.py : the Brian2 simulation script of single-layer fully-connected SNN using the homeostasis method proposed by the author of this repository.
- file_rename.sh : bash shell for rename and move the simulation file.
- evaluation/accuracy_evaluation.py : the python script for processing the simulation results (spike history) and get the training and testing accuracy using the simple vote mechanism.
- evaluation/weight_visualization.py : the python script for visualizing the learned weight during training.
- evaluation/spike_counter.py : the python script for recording the spike number during training.
- evaluation/spike_counter_visualization.py : the python script for visualization the spike number during training.
- evaluation/testing_accuracy.py : a python script for reading the testing accuracy after every training iteration. This script should be copied to the corresponding simulation folder, so you should check the relative route before running it.
- evaluation/spike_standard_deviation.py : a python script for calculating the spike number deviation after every training iteration. This script should be copied to the main folder, so you should check the relative route before running.
## source file description in Spike generation
- spike_generation_run.sh : the top-level bash shell for running the spike generation python script.
- spike_recorder_focal.py : the Brian2 simulation script for generating the spike train for MNIST dataset.
Before running the spike generation script, MNIST dataset should be saved in a folder "dataset_mnist" along with the folder "Spike generation".
## User guide
The code is tested in bash on Ubuntu 16.04. The top-level script 'talent_run.sh' include most of the scripts for simulation and data process. You just need to run the 'spike_generation_run.sh' shell script to generate the spike train you need for simulation.
For example, if you want to simulate the SNN learning algorithm with 10000 training examples and 1000 testing examples. Firstly, you should run the spike generation script to generate the spike train of 10000 training examples and 1000 testing examples separately.
Secondly, run the 'talent_run.sh' in terminal, and input the simulation parameters as recommended.
