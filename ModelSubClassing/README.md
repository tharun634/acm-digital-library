# Model SubClassing and Custom Training in Keras

If you are a Deep Learning enthusiast, or are looking to get into Deep Learning, you would probably heard of the magical framework for Deep Learning that is Tensorflow (and maybe PyTorch too, but we'll focus on Tensorflow for now xD). 

Creating your first model can be tough, especially if you're an absolute beginner. Fortunately, Tensorflow 2.x allows you to use Keras as a high level API to create your models. Still that doesn't help you as you still need to know how make a model first. In this document, we will first explore the different methods of model creation in Tensorflow, and their pros and cons, and then we will learn how create a custom training loop.

## Different APIs for creating models:

Tensorflow 2.x and Keras have 3 separate APIs to make models

1. [Sequential API](Sequential/README.md)
2. [Functional API](Functional/README.md)
3. [SubClassing API & Custom Loop Creation](SubClassing/README.md) 
   
Depending on your proficiency level, you can follow through the whole document, or jump directly to the section you want to learn. 

## Data Pipeline 

Before getting into model creation, lets first create a data pipeline. For simplicity, we will be using MNIST, but you can structure your model for any other dataset you want. 

### Importing Libraries
```py
import numpy as np
import matplotlib.pyplot as plt 

import tensorflow as tf 
from tensorflow.keras import models, layers

from sklearn.model_selection import train_test_split
```

### Loading Data 
```py
(x_train, y_train), (x_test, y_test) = tf.keras.datasets.mnist.load_data()

x_train = np.expand_dims(x_train, -1)
x_train = x_train.astype(np.float32)/255. 

x_test = np.expand_dims(x_test, -1)
x_test = x_test.astype(np.float32)/255. 

x_train, x_val, y_train, y_val = train_test_split(
    x_train, y_train, 
    test_size = 0.1, 
    shuffle = True, random_state = 1000
)

print("Training Input shape: ", x_train.shape)
print("Validation Input shape: ", x_val.shape)
print("Test Input shape: ", x_test.shape)

# Output:
# Training Input shape:  (54000, 28, 28, 1)
# Validation Input shape:  (6000, 28, 28, 1)
# Test Input shape:  (10000, 28, 28, 1)
```

### Initializing Tensors
```py
train_gen = tf.data.Dataset.from_tensor_slices((x_train, y_train))
train_gen = train_gen.batch(batch_size = 32).shuffle(buffer_size = 1000)

val_gen = tf.data.Dataset.from_tensor_slices((x_val, y_val))
val_gen = val_gen.batch(batch_size = 32).shuffle(buffer_size = 1000)

test_gen = tf.data.Dataset.from_tensor_slices((x_test, y_test))
test_gen = test_gen.batch(batch_size = 32).shuffle(buffer_size = 1000)
```

Jump To: 

1. [Sequential API](Sequential/README.md)
2. [Functional API](Functional/README.md)
3. [SubClassing API and Custom Loop Creation](SubClassing/README.md) 

For more information, check out the following links:

1. [Writing a custom training loop](https://www.tensorflow.org/guide/keras/writing_a_training_loop_from_scratch)
2. [Model SubClassing](https://www.tensorflow.org/guide/keras/custom_layers_and_models)