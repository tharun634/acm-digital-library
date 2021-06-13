# Sequential API

This is the simplest method of constructing models. It can be used for small and simple models with a not very complicated architecture, like a basic CNN (which is what we will be building). 

## Sequential Model Function
```py
def sequentialModel(input_shape = (28, 28, 1)):

    model = models.Sequential([
        layers.Conv2D(filters = 32, kernel_size = (3, 3), input_shape = input_shape),
        layers.BatchNormalization(),
        layers.Activation("relu"),
        layers.MaxPool2D(2, 2),

        layers.Conv2D(filters = 64, kernel_size = (3, 3)),
        layers.BatchNormalization(),
        layers.Activation("relu"),
        layers.MaxPool2D(2, 2),

        layers.Flatten(),
        layers.Dense(10, activation = 'softmax')
    ])

    return model 
```

<div style="text-align: center">
<img src="seqModelArch.png" alt="Sequential Model Architecture" style="margin: 5% auto;">
</div>

## Compiling and Training 
```py
seqModel = sequentialModel()
seqModel.summary()

seqModel.compile(
    optimizer = tf.keras.optimizers.Adam(learning_rate = 0.00005),
    loss = tf.keras.losses.SparseCategoricalCrossentropy(),
    metrics = ['accuracy']
)

seqHist = seqModel.fit(train_gen, validation_data = val_gen, epochs = 10)

# Output: 
# ...
# Epoch 9/10
# 1688/1688 [==============================] - 6s 3ms/step - loss: 0.0358 - accuracy: 0.9902 - val_loss: 0.0468 - val_accuracy: 0.9857
# Epoch 10/10
# 1688/1688 [==============================] - 6s 3ms/step - loss: 0.0326 - accuracy: 0.9911 - val_loss: 0.0447 - val_accuracy: 0.9875
```

## Evaluation
```py
seqModel.evaluate(test_gen)

# Output: 
# 313/313 [==============================] - 1s 2ms/step - loss: 0.0399 - accuracy: 0.9882
```

This was a pretty simple model with 2 convolution and maxpooling layers along with batch-normalization, with everything connected sequentially. The sequential API is best suited for small networks like this. 

The drawback is that a sequential API doesn't give you much flexibility in changing the model parameters. You can only stack layers on top of each other. 

Consider if you want to build a network with [residual connections](https://towardsdatascience.com/residual-blocks-building-blocks-of-resnet-fd90ca15d6ec). How would you do this?

Check out the [Functional API](../Functional/README.md)

Jump To: 

1. [Home](../)
2. [Functional API](../Functional/)
3. [SubClassing API and Custom Loop Creation](../SubClassing/) 
