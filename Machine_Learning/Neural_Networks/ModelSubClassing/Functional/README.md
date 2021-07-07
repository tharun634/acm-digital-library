# Functional API: 

The functional API is a method of model creation where each layer can be thought of as a function, which accepts the outputs of the previous layer as its input parameters. Its slightly similar to the sequential API in terms of implementation, but offers much more flexibility in model creation. Using this, you can create residual connections, inception modules, and more complicated architectures. 

We will be checking out a simple Residual network using the functional API:

## Functional Model function:

```py
def functionalModel(input_shape = (28, 28, 1)):

    inp = layers.Input(shape = input_shape)
    
    mainBranch = layers.Conv2D(32, (3, 3), padding="same")(inp)
    mainBranch = layers.BatchNormalization()(mainBranch)
    mainBranch = layers.Activation("relu")(mainBranch)
    mainBranch = layers.MaxPool2D(2, 2)(mainBranch)
    
    branch1 = layers.Conv2D(32, (3, 3), padding="same")(mainBranch)
    branch1 = layers.BatchNormalization()(branch1)
    branch1 = layers.Conv2D(32, (3, 3), padding="same")(branch1)
    branch1 = layers.BatchNormalization()(branch1)

    mainBranch = layers.Add()([mainBranch, branch1])
    mainBranch = layers.Activation("relu")(mainBranch)
    mainBranch = layers.Conv2D(64, (3, 3), padding="same")(mainBranch)
    mainBranch = layers.MaxPool2D(2, 2)(mainBranch)

    flat = layers.Flatten()(mainBranch)
    dense = layers.Dense(10, activation = "softmax")(flat)

    model = models.Model(inputs = inp, outputs = dense)
    return model
```
<div style="text-align: center">
<img src="funcModelArch.png" alt="Functional Model Architecture" style="margin: 5% auto;">
</div>

## Compiling and Training 
```py
funcModel = functionalModel()
funcModel.summary()

funcModel.compile(
    optimizer = tf.keras.optimizers.Adam(learning_rate = 0.00005),
    loss = tf.keras.losses.SparseCategoricalCrossentropy(),
    metrics = ['accuracy']
)

funcHist = funcModel.fit(train_gen, validation_data = val_gen, epochs = 10)

# Output
# ...
# Epoch 9/10
# 1688/1688 [==============================] - 7s 4ms/step - loss: 0.0276 - accuracy: 0.9920 - val_loss: 0.0445 - val_accuracy: 0.9865
# Epoch 10/10
# 1688/1688 [==============================] - 7s 4ms/step - loss: 0.0246 - accuracy: 0.9929 - val_loss: 0.0418 - val_accuracy: 0.9868
```

## Evaluation 
```py
funcModel.evaluate(test_gen)

#Output
# 313/313 [==============================] - 1s 2ms/step - loss: 0.0381 - accuracy: 0.9878
# [0.03806757554411888, 0.9878000020980835]
```


The Functional API builds the model as a DAG (Directed Acyclic Graph) of layers. Though this is true for most architectures, it cannot be used for models which apply recursive networks.

Moreover, we can add more customizability to our layers (at the cost of being a little more verbose) using the [SubClassing API](../SubClassing/README.md).

Jump To: 

1. [Home](../)
2. [Sequential API](../Sequential/)
3. [SubClassing API and Custom Loop Creation](../SubClassing/) 

