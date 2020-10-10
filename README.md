# How to use the scripts
The script titled `cnn_training_loops.ipynb` contains the training loops we used to train both the
MNIST model and the CIFAR model. 

## MNIST
Here we found good values for hyperparameters online to use for our CNN to classify images from the
MNIST dataset. Thus, we simply had a single training loop with 5 epochs.

## CIFAR
The bulk of this file pertains to the CIFAR dataset. Before training the model with optimal hyperparameters,
we had to determine what those values were.

The first training loop optimizes the batch size. We tried different values for a batch size and recorded
the testing and training losses.

The second training loop optimizes the learning rate. Again, we tried different values for a learning
rate and recorded the testing and training losses.

The third training loop optimizes momentum. Again, we tried values and recorded losses.

The last training loop is when we train our final model using the optimal hyperparameters. We chose
a batch size of 512, a learning rate of 0.01, and a momentum of 0.3. At the time of this writing,
our model has trained for 100 epochs, but will likely be trained for more by the time of
submission.

## Inferencing
To make inferences with our models, simply run the script `use_models.ipynb`. 

**NOTE:** It is possible when running our script that Jupyter notebook
quits when trying to unpickle our variables due to their size. If this happens, start jupyter notebook
with the following parameter set:

`jupyter notebook --NotebookApp.iopub_data_rate_limit=1.0e10`

The first part will load the
MNIST testing set and our MNIST model, make inferences on all images using our model, then output the
average loss and overall accuracy. The next part of the script will do the same for the CIFAR testing set.
Lastly, we graph the results of recording the testing and training losses when optimizing each parameter.

At the end of the file is our answers to the written portions of questions 5 and 6.
