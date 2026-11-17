# **Error Backpropagation in Neural Networks**

## **1. Introduction**

**Error Backpropagation (Backward Propagation)** is a learning algorithm used to train artificial neural networks by reducing the difference between the actual output and predicted output.

It works by calculating the error at the output layer and propagating that error backward through the hidden layers to adjust the weights and biases.

The main objective of error backpropagation is to minimize the loss function and improve the accuracy of the neural network.

**Simple definition:** Error backpropagation is a process of sending prediction errors backward through a neural network to calculate gradients and update weights to reduce errors.

[18.2 Optimizers — CMSC320 Section Dr. Alam](https://images.openai.com/static-rsc-4/qPLjMf1X_yB0M6dAVrXYwBnu2Li5LAOeCVoRNP4pBxz9kuLGCO4i5MsNBVGBC_7n48qOi9bSPwhHRSpat4JXTMoDLXq0AvuFAtRj0pf3IaC3kJyD2zYLmbCUBZbAMX3cQHuNizghOBRqUow-s1mzaJuQX4YlzZ27bCtQfUvXKok?purpose=inline)

[ffalam.github.io](https://ffalam.github.io/CMSC320TextBook/chapter18/Chapter18_7.html?utm_source=chatgpt.com)

## **2. Basic Concept of Error Backpropagation**

A neural network produces an output after processing input data. Sometimes, the predicted output is different from the actual output.

For example:

- Actual output = 1
- Predicted output = 0.6
- Error = 0.4

The network must reduce this error to improve its prediction.

Error backpropagation helps the network identify how much each weight contributes to the error and adjusts the weights accordingly.

## **3. Architecture of Error Backpropagation**

A basic neural network contains three layers:

1. Input Layer
2. Hidden Layer
3. Output Layer

[Backpropagation: How Neural Networks Learned to Learn | by Ignacio Quintero | Medium](https://images.openai.com/static-rsc-4/bOyqVl_Cx_UMKKkteZwcTNbjBqSD4lcNJ7CjvxYWIEfSGcPvyYDR2_KN0xiayhpK1PbZovrmEXqTEqE5YBrpcrqdOs7YQ1sFCKdSSBkyEyEzXCXeCXjjNJtAGoElBcknnPeBIy-tiU9odJJ5UKgDDY16yOFuoFbYqMZhMlIn2sw?purpose=inline)

[medium.com](https://medium.com/%40igquinteroch/backpropagation-how-neural-networks-learned-to-learn-8f0d6654e914?utm_source=chatgpt.com)

**Working:**

- Input layer receives the data.
- Hidden layer processes the information.
- Output layer produces the predicted result.
- Loss function calculates the error.
- Error is propagated backward.
- Weights and biases are updated.

## **4. Steps Involved in Error Backpropagation**

There are six important steps.

### **Step 1: Initialize Weights and Biases**

- Assign initial values to weights and biases.
- Weights are generally initialized with small random values.
- These values are adjusted during training.

### **Step 2: Forward Propagation**

- Input data is supplied to the input layer.
- Each input is multiplied by its corresponding weight.
- Bias is added to the weighted sum.
- Activation functions are applied.
- The output layer generates the predicted result.

### **Step 3: Calculate Error (Loss Function)**

The predicted output is compared with the actual output.

A common loss function is Mean Squared Error (MSE).

\\[ E=\frac{1}{2}(T-O)^2 \\]

Where:

- \\(E\\) = Error
- \\(T\\) = Target or actual output
- \\(O\\) = Predicted output

**Example:**

Actual output = 1

Predicted output = 0.6

\\[ E=\frac{1}{2}(1-0.6)^2 \\]

\\[ E=\frac{1}{2}(0.16) \\]

\\[ \boxed{E=0.08} \\]

### **Step 4: Backward Propagation of Error**

- The calculated error is propagated from the output layer toward the input layer.
- The network uses the chain rule of differentiation.
- Gradients are calculated for each weight and bias.
- These gradients indicate how the parameters affect the total error.

[From Aristotle to Artificial Intelligence: How the Sudden Intersection of Philosophy, Computing Power, and Algorithms Transformed the Future of Intelligence | by Isabela Umaña Costa | Medium](https://images.openai.com/static-rsc-4/l-lX0TCc4Hnq2ow2HT8XIPWg2z5tzLX53P9DVbjB5izR52w6Ao5DbJLzaJ96HV5ofag5McffaXDmdW5dTlZ64wQKreLmOoA6QFqbjoISA9z7dbr1GBiapr9f0OlNEKy1rjaArFxnJ9F5Xj9q8YAIyy7D8fUEDwS7qmI055KZ8M0?purpose=inline)

[medium.com](https://medium.com/%40umanaisabela/from-aristotle-to-artificial-intelligence-how-the-intersection-of-philosophy-hardware-and-3a3af85e4e9a?utm_source=chatgpt.com)

### **Step 5: Update Weights and Biases**

The weights are adjusted to reduce the error.

Weight update equation:

\\[ W\_{new}=W\_{old}-\eta\frac{\partial E}{\partial W} \\]

Bias update equation:

\\[ b\_{new}=b\_{old}-\eta\frac{\partial E}{\partial b} \\]

Where:

- \\(W\\) = Weight
- \\(b\\) = Bias
- \\(\eta\\) = Learning rate
- \\(E\\) = Error function

The learning rate determines how much the weights change during each update.

### **Step 6: Repeat the Process**

- Updated weights are used for the next forward propagation.
- The error is calculated again.
- Backpropagation updates the weights repeatedly.
- The process continues until the error is sufficiently minimized.

## **5. Flowchart of Error Backpropagation**

[Mastering Backpropagation: A Comprehensive Guide for Neural Networks | DataCamp](https://images.openai.com/static-rsc-4/DgikuCbIOUmdfEu5S-eFtB813vDtkI0cN5K3JoEG72W0cwOxdEu6CVOSWAa4mstXckjbjvJS_DFKx5Izw2DieFMSl8a6dKuQhR6DyO8ov0bKJg7gPcSV-tr0lM96VmYPBpV6memAUmtS01O51_BG78_totRhLe53B_Y95ZczBT8?purpose=inline)

[datacamp.com](https://www.datacamp.com/tutorial/mastering-backpropagation?utm_source=chatgpt.com)

**Sequence:**

1. Start.
2. Initialize weights and biases.
3. Give input data.
4. Perform forward propagation.
5. Calculate output error.
6. Propagate error backward.
7. Calculate gradients.
8. Update weights and biases.
9. Check the error.
10. Repeat until the desired accuracy is achieved.

## **6. Role of Activation Functions**

Activation functions play an important role in error backpropagation because their derivatives are used to calculate gradients.

Common activation functions include:

| Activation function | Purpose                                   |
| ------------------- | ----------------------------------------- |
| Sigmoid             | Produces values between 0 and 1           |
| ReLU                | Converts negative values into zero        |
| Tanh                | Produces values between -1 and +1         |
| Softmax             | Converts output scores into probabilities |

## **7. Advantages of Error Backpropagation**

1. Reduces prediction errors.
2. Improves neural network accuracy.
3. Automatically adjusts weights and biases.
4. Helps neural networks learn complex patterns.
5. Works with multiple hidden layers.
6. Supports different optimization algorithms.

## **8. Disadvantages of Error Backpropagation**

1. Requires high computational power for large networks.
2. Training can take a long time.
3. May suffer from vanishing gradients.
4. May suffer from exploding gradients.
5. Requires proper selection of learning rate.
6. Performance depends on training data and network architecture.

## **9. Applications of Error Backpropagation**

[Introduction to Neural Networks and Deep Learning | PPTX](https://images.openai.com/static-rsc-4/ahO53yBywWjhhPOATWQuWWOTYYEa4rF1-lxdkyNcmsptFROjy3geiy_Qrcb8ksPyh1KKkBCmTMh4FGgwV_kaoDL6PTRzFBE6dkc7KHwqKjnETB0bNRYCa4CTPSnas9cUvps0mvTKwc5hQaxa77hLzajElZEtdb0dL8TvJQzND9Q?purpose=inline)

[Transfer learning: harnessing the power of pre-trained models for business success](https://images.openai.com/static-rsc-4/YpFc_cUxhpDZLzteiB4Xr5raWVyCrvwgW7_fUxFAq_Wc8CO2GXb_8MtRWBDU6200up9SGtgs7qsKiLAJhGgRAiAP6-MSWp_Id38aMSvgj1oTazMTigRKrCM2AdcG-nNvV6mmBknc3snNgnuErLWXyUtRNC9aA8X_U_nc9j1MvSg?purpose=inline)

[AICS First Submission in NIST’s Face Recognition Test – AICS](https://images.openai.com/static-rsc-4/6-ZQNgWbQ-mBUuL6QBUAndP3PD5wixvLQdcEFDGliFwOEjY9yq1WHaSfDMS--PanZqH5G71uRuieKlfYvc1GnVwE1owR78stVGHawOvQQRIVDSC3DHYlw3AAq_wC0Vs1X0T-UNXmdaWn7SpEZZWsGyX7P9M7tbsIzwqy9ScGEWI?purpose=inline)

7

1. Image recognition.
2. Face detection.
3. Speech recognition.
4. Medical diagnosis.
5. Pattern recognition.
6. Wireless signal classification.
7. Prediction and data analysis.

## **10. Difference Between Forward Propagation and Error Backpropagation**

| Forward Propagation         | Error Backpropagation            |
| --------------------------- | -------------------------------- |
| Moves from input to output  | Moves from output toward input   |
| Calculates predicted output | Calculates gradients             |
| Uses current weights        | Helps update weights             |
| Calculates the loss         | Helps minimize the loss          |
| Performs prediction         | Performs learning and correction |

## **11. Conclusion**

Error backpropagation is an important learning algorithm used in artificial neural networks. It calculates the difference between actual and predicted outputs and propagates the error backward through the network. Using gradients and weight updates, it minimizes the loss function and improves the performance of the neural network.

Important for 10/13-mark examination

### **Key points to remember**

1. Initialize weights and biases.
2. Forward propagation.
3. Error calculation.
4. Backward propagation.
5. Gradient calculation.
6. Weight and bias updating.
7. Repeat the process.

**Most important formulas:**

Error function:

\\[ E=\frac{1}{2}(T-O)^2 \\]

Weight update:

\\[ W\_{new}=W\_{old}-\eta\frac{\partial E}{\partial W} \\]

### **Important difference to remember**

- **Error Backpropagation:** Calculates gradients by propagating errors backward.
- **Gradient Descent:** Uses those gradients to update weights and minimize the error.

Both work together to train a neural network.
