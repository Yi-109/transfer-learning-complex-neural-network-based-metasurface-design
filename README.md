# transfer-learning-complex-neural-network-based-metasurface-design
Requirements
====
We recommend using python3.6 and pycharm. 
We recommend resetting a new environment for transfer-learning-complex-neural-network-based-metasurface-design, eg:python3.6(pytorch)
We recommend using tensorboard to visualize and log the training process.

Introduction
====
The project is mainly divided into three parts: 1.Source Model Construction；2.Transfer Knowledge to Target Model；3.On-demand Metasurface Design via CAPSO.
There are also some files for data processing, complex number calculation and result visualization.

Source Model Construction
-------
In this part, the complex neural network is trained on the open source datasets referenced in the manuscript.
Model definition: ./models/predict.py
Dataset partition:. /utils/divide.py
Data processing and loading: ./data/dataset.py
Training the model: ./train.py
Testing the model: ./test.py

Transfer Knowledge to Target Model
-------
In this part, the well-trained hyperparameters are transferred to the target model, and the network is trained on the homemade small dataset.
Model definition: ./models/TransferPredict.py
Dataset partition: ./utils/divide.py
Data processing and loading: ./data/dataset.py
Training the model: ./transfer_train.py
Testing the model: ./transfer_test.py

On-demand Metasurface Design via CAPSO
-------
In this part, the trained target model is regarded as the surrogate model of CST, and the ideal phases and amplitudes for the meta-device are taken as optimization targets to iteratively solve the optimal geometric parameters of the meta-atoms at each position.
Main program: pso_optimize.py
Function file: pso_transfer.py

