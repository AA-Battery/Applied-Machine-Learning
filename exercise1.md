# Answers to prompts:

### According to Maroney, what is the difference between traditional programming and machine learning?

Traditional programming involves inputing rules and data into a machine to produce answers. However, machine learning restructures this relationship. Machine learning involes inputing data and answers into a machine to produce rules. This means that the programmer does not need to establish the rules themselves. 

### Modify the predict function to produce the output for the value 7. Do this twice and provide both answers. Are they the same? Are they different? Why is this so?

The two answers my network prediction for the input 7 were: 12.986899 and 12.992102. These two values are very similar, however slightly different because the network adopted slightly different parameters for each time it was trained, therefore producing different answers. The network will always output answers extremely close to 13, however they will almost always be different values because the neurons in the network have adopted different weights and biases through training. 

### Based on this model, which of the six homes present a good deal? Which one is the worst deal? Justify your answer.

import pandas as pd
import numpy as np
import tensorflow as tf
from tensorflow import keras

model = tf.keras.Sequential([keras.layers.Dense(units=1,input_shape=[2])])

model.compile(optimizer='sgd',loss='mean_squared_error')

#### Number of bedrooms
x1 = np.array([4.0,3.0,4.0,5.0,2.0,3.0],dtype=float)
#### Square-footage
x2 = np.array([3.524,2.840,3.860,3.510,1.479,1.238],dtype=float)
xs = np.stack([x1,x2], axis=1)

#### Price
ys = np.array([2.89,2.29,3.99,3.475,2.5,0.97],dtype=float)

model.fit(xs,ys,epochs=1000)

#### Training sample one
a = np.array([4.0],dtype=float)
b = np.array([3.524],dtype=float)
c = np.stack([a,b], axis=1)

print(model.predict([c]))

#### Output is 3.3303, which is higher than the price in the training data (y=2.89). Therefore, the listed price in the training data is a good deal.

#### Training sample five
a = np.array([2.0],dtype=float)
b = np.array([1.479],dtype=float)
c = np.stack([a,b], axis=1)

print(model.predict([c]))

#### Output is 1.6727, which is lower than the price in the training data (y=2.5). Therefore, the listed price in the training data is a bad deal. This is the worst deal in my opinion because the listed price is inflated almost 40% higher than the price the network predicts. This is the highest percentage markup. Also this house has the fewest bedrooms.
