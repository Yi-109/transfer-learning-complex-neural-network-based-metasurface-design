# transfer-learning-complex-neural-network-based-metasurface-design
Requirements
====
We recommend using python3.6 and pycharm. <br>
We recommend resetting a new environment for transfer-learning-complex-neural-network-based-metasurface-design, eg:python3.6(pytorch).<br>
We recommend using tensorboard to visualize and log the training process. <br>

Introduction
====
The project is mainly divided into three parts: 1.Source Model Construction；2.Transfer Knowledge to Target Model；3.On-demand Metasurface Design via CAPSO.<br>
There are also some files for data processing, complex number calculation and result visualization. <br>
Main program for part1 and part2: ./main.py <br>
Configuration file: ./config.py <br>

1.Source Model Construction
-------
In this part, the complex neural network is trained on the open source datasets referenced in the manuscript.<br>
Model definition: ./models/predict.py <br>
Dataset partition:. /utils/divide.py <br>
Data processing and loading: ./data/dataset.py <br>
Training the model: ./train.py <br>
Testing the model: ./test.py <br>

2.Transfer Knowledge to Target Model
-------
In this part, the well-trained hyperparameters are transferred to the target model, and the network is trained on the homemade small dataset.<br>
Model definition: ./models/TransferPredict.py <br>
Dataset partition: ./utils/divide.py <br>
Data processing and loading: ./data/dataset.py <br>
Training the model: ./transfer_train.py <br>
Testing the model: ./transfer_test.py <br>

3.On-demand Metasurface Design via CAPSO
-------
In this part, the trained target model is regarded as the surrogate model of CST, and the ideal phases and amplitudes for the meta-device are taken as optimization targets to iteratively solve the optimal geometric parameters of the meta-atoms at each position. <br>
Main program: ./pso_optimize.py <br>
Function file: ./pso_transfer.py <br>

