# **Convolutional Neural Network (CNN)**

## **1. Introduction**

A **Convolutional Neural Network (CNN)** is a type of Deep Learning algorithm mainly used for processing and analyzing images and visual data.

It is inspired by the human visual system. CNN automatically identifies important features from images, such as edges, shapes, textures, and objects.

CNN is widely used in:

- Image recognition
- Face detection
- Object detection
- Medical image analysis
- Handwriting recognition
- Autonomous vehicles
- Wireless signal classification

**Example:** When we give a CNN an image of a cat, it identifies the features of the image and predicts that the image contains a cat.

[Convolutional Neural Networks Explained Simply: From Pixels to Powerful Vision AI | by Damodaran Selvaraj | Mar, 2026 | Medium](https://images.openai.com/static-rsc-4/lOT023TtNQAacPHhpobIeWNHxZ3cgjxMUybDyMh5-vIAeaqqpncVLf6aAnaoT5L1o17y3IIA5qVJyykKbjkxjGshWX9IWDz9UAZX1CUBj2z3Lrb5lvbhlNWtB4REG95vFaB0p9mMXGuIMUHO5wAZT_Q0f0wPumz93r-Hjr1f8aA?purpose=inline)

[medium.com](https://medium.com/%40damodaran.selvaraj/convolutional-neural-networks-explained-simply-from-pixels-to-powerful-vision-ai-f6e3cba01b8d?utm_source=chatgpt.com)

## **2. Architecture of CNN**

A CNN consists of several layers that process input data step by step.

[What are Convolutional Neural Networks (CNN)? The Art of Computer Vision For Beginners - DEV Community](https://images.openai.com/static-rsc-4/CAK9tIrb-FiSWk9tDHQ5Z1UYbxRoF19C0PTBLvft-CViRAc1HsyPudwKN2gjvD1H_gcu70hQDcXHBwrgs2r4_mXZkizcnF7E5hda77z951QNyEZNixQ0MunWbIqhJt2TN-Hwt2k3UKNB4U2q3Rl0eNSoU93FyVgLV2gan46FAmQ?purpose=inline)

[dev.to](https://dev.to/saidi-souhaieb/what-are-convolutional-neural-networks-cnn-the-art-of-computer-vision-for-beginners-34nn?utm_source=chatgpt.com)

The main layers of CNN are:

1. Input Layer
2. Convolutional Layer
3. ReLU Activation Layer
4. Pooling Layer
5. Flattening Layer
6. Fully Connected Layer
7. Output Layer

Let's understand each layer.

## **3. Layers of CNN**

### **1. Input Layer**

- The input layer receives the image or data.
- An image is represented as a collection of pixels.
- Each pixel contains numerical values representing its color or intensity.

**Example:** A grayscale image of size 28 × 28 contains 784 pixel values.

[An Introduction to Convolutional Neural Networks: A Comprehensive Guide to CNNs in Deep Learning | DataCamp](https://images.openai.com/static-rsc-4/e_qqHfqV-sxOGjZK-Dm9j8xbRUKgQ0bGj5IQqtb0l1RJRWTf1aWVi79tGMdfA439rikGziaTOw6ZZS_dBC1Vo_9dv44zsD-OxBGZtM1QRClsmQ3r0Ug8hRyvxtQ4LxpQzduzisJFnpRWyK-X5a3YZ7EJ3A5M5k75RrXI2OvlulE?purpose=inline)

[datacamp.com](https://www.datacamp.com/tutorial/introduction-to-convolutional-neural-networks-cnns?utm_source=chatgpt.com)

### **2. Convolutional Layer**

- It is the most important layer in CNN.
- It extracts features from the input image.
- It uses a small matrix called a **filter or kernel**.
- The filter moves across the image and performs multiplication and addition operations.
- It produces a feature map.

**Example:** Detecting edges, lines, curves, and shapes in an image.

[Convolutional Neural Network (CNN) Architecture Explained in Plain English Using Simple Diagrams | by Rukshan Pramoditha | TDS Archive | Medium](https://images.openai.com/static-rsc-4/BFcEV8OYmdl2n1ldnRRIZgTUnvN3YM1venCQejFVLeuHYcf8x2NKRl5fDskoke9bu2fVMSkRynCiWlh2lIR9znl32o8aHsy-IqNQe5lGFXLACXmzyz3Ee_HkGaheFgjmx2Pu6mAtfmt5ID77I2qbucrElwNx_2pqttNa3zKTWQ0?purpose=inline)

[medium.com](https://medium.com/data-science/convolutional-neural-network-cnn-architecture-explained-in-plain-english-using-simple-diagrams-e5de17eacc8f?utm_source=chatgpt.com)

**Important keywords:**

- Filter / Kernel
- Feature Map
- Stride
- Padding
- Convolution Operation

### **3. ReLU Activation Layer**

ReLU stands for **Rectified Linear Unit**.

- It introduces non-linearity into the neural network.
- It converts negative values into zero.
- Positive values remain unchanged.

Mathematical expression:

\\[ f(x)=\max(0,x) \\]

Example:

| Input | ReLU Output |
| ----- | ----------- |
| -5    | 0           |
| -2    | 0           |
| 0     | 0           |
| 3     | 3           |
| 8     | 8           |

**Purpose:** Helps the network learn complex patterns and features.

### **4. Pooling Layer**

- Pooling reduces the size of feature maps.
- It reduces computational complexity.
- It retains important features.
- It helps reduce overfitting.

There are two common types:

**A. Max Pooling**

Selects the maximum value from a particular region.

Example:

[Seeing the World: A Beginner's Guide to Convolutional Neural Networks (CNNs) with PyTorch - DEV Community](https://images.openai.com/static-rsc-4/FtBOsCE4g43pIPwKhyatWmdIWuhhZycz7jdx7MXY322YoQJO-4hW1dXtqa-7qAGedgg2VzCsQjyyGa62uaKHJFKXbBMdNxtJx4RIivC0AsTKzpA8UmiGYDQloYu3rK-jLSNLJ4JhQ2YjRthjvVoTDzpWAzaPiSNJDIAbCP-VwaY?purpose=inline)

[dev.to](https://dev.to/saadmanrafat/seeing-the-world-a-beginners-guide-to-convolutional-neural-networks-cnns-with-pytorch-593c?utm_source=chatgpt.com)

Input:

\\[ \begin{bmatrix} 1&3&2&4\\\ 5&6&1&2\\\ 7&8&3&4\\\ 2&1&5&6 \end{bmatrix} \\]

After 2 × 2 Max Pooling:

\\[ \begin{bmatrix} 6&4\\\ 8&6 \end{bmatrix} \\]

**B. Average Pooling**

Calculates the average value of each region.

For example:

\\[ \frac{1+3+5+6}{4}=3.75 \\]

### **5. Flattening Layer**

- Converts the 2D feature maps into a 1D vector.
- It prepares the extracted features for the fully connected layer.
- It connects the convolutional part with the classification part.

[The Flattening and Full Connection Steps of Convolutional Neural Networks | Nick McCullum](https://images.openai.com/static-rsc-4/8tes59i-ETSEby8oXqbAk7BjsoeqbtUCfAlfo2I19it3Nw_krES9O5n8tSjKeUllsK56d_zpMSflO8-hrqX9Rbp6PLUXxY993GjKvl94zaT7v5gBn5mI8OR1U773GdlDFkqfw6CNGY2kF6l6NjDBoY9zpKrxd6r__gz0xqQoPgc?purpose=inline)

[nickmccullum.com](https://www.nickmccullum.com/python-deep-learning/flattening-full-connection/?utm_source=chatgpt.com)

### **6. Fully Connected Layer**

- All neurons are connected to the neurons in the next layer.
- It uses the extracted features to perform classification.
- It learns relationships between the features and output classes.

**Example:** Determines whether an image represents a cat, dog, or bird.

### **7. Output Layer**

- Produces the final prediction.
- It provides the probability or classification result.
- Softmax is commonly used for multi-class classification.

Example:

| Object | Probability |
| ------ | ----------- |
| Cat    | 85%         |
| Dog    | 10%         |
| Bird   | 5%          |

Final prediction: Cat.

## **4. Working Principle of CNN**

[What is Convolutional Neural Network — CNN (Deep Learning) | by Kh. Nafizul Haque | Medium](https://images.openai.com/static-rsc-4/koAywMNOQup4Tsm93-BTjbutKduZ_CQzRHVJYuLbr9I1wYbeER-EPY5j3BE9w68zn532bt-MiDpqv_8XIWq2OTBlkdEN0NNaz-NgMpKGRbLPqQP7Jwt6x34v00FDUVBy6l8tM73VNwVznLWWsJcCgJ4W2uakDPC8IpbY_4xsC-M?purpose=inline)

[nafizshahriar.medium.com](https://nafizshahriar.medium.com/what-is-convolutional-neural-network-cnn-deep-learning-b3921bdd82d5?utm_source=chatgpt.com)

The working process is:

1. Input image is given to the CNN.
2. Convolution layer extracts important features.
3. ReLU removes negative values.
4. Pooling reduces the feature map size.
5. Flattening converts feature maps into a vector.
6. Fully connected layer performs classification.
7. Output layer gives the final result.

## **5. Applications of CNN**

[영상과 이미지 인식 분야에 탁월한 CNN (Convolutional Neural Network)](https://images.openai.com/static-rsc-4/MjAbWorw7lG5skH6FPBDbMw9l74IqGBJ5iVV4hF8iYfnuLoA4kmyoOAlpU3XqEqhV-IlEBOEyNj5ZmKXp_Egd-M5zm0Ywq_7nJXc_tgRUGwzFm3wJLiDNB7L2QxIPCcR4N6tWY5vKpcttSe0iRc1O0LbjUnDkdmucZCbWYtgC9g?purpose=inline)

[Convolutional Neural Networks (CNN) in Self-Driving Cars](https://images.openai.com/static-rsc-4/ZG1rgODo7L2eocPvtvTwN7B0yYqL3bakGukZAB4KJXAMnq-POXkIciMrtTtgP8QDsh3bbQrhKTKOuUfIt15ZHcpdPMA4il9HuhlzciUfCkug4chA3zXJg42VR7kg0gpTAZNEqDuJNq5ruhONl1c3QfPAb4FT27C9KejEurjBNGQ?purpose=inline)

[An Efficient Multi-Scale Convolutional Neural Network Based Multi-Class Brain MRI Classification for SaMD | MDPI](https://images.openai.com/static-rsc-4/-9bcK4QXefCJ3ndiQhm8RzIpGLb3QxvMM2AWUrX6yT5WqNYf5YhtTmjGBvVEr8JBNtgu3QlYj2XDGvI38GXMN7Ro8HyeZ1znoGb13JVc44tq2H0S3JsY3jCxT2t8p3tirJFZXShBV2IGLnun19A5RXwVrQIb43MkzaXCpVkp6Lo?purpose=inline)

6

1. **Face Recognition:** Identifies and recognizes human faces.
2. **Medical Imaging:** Detects diseases from X-rays and MRI scans.
3. **Object Detection:** Identifies objects in images and videos.
4. **Self-Driving Cars:** Detects roads, vehicles, pedestrians, and traffic signs.
5. **Handwriting Recognition:** Recognizes handwritten letters and numbers.
6. **Wireless Communication:** Classifies modulation types and analyzes wireless signal patterns.

## **6. Advantages of CNN**

1. Automatically extracts important features.
2. Provides high accuracy in image recognition.
3. Reduces manual feature extraction.
4. Handles large image datasets.
5. Learns complex patterns.
6. Useful for real-time object recognition.

## **7. Disadvantages of CNN**

1. Requires a large amount of training data.
2. Requires high computational power.
3. Training can take a long time.
4. Requires memory and processing resources.
5. Designing the network architecture can be difficult.

## **8. Important Terms in CNN**

| Term        | Explanation                                    |
| ----------- | ---------------------------------------------- |
| Kernel      | Small matrix used to extract features          |
| Convolution | Operation used to extract image features       |
| Feature Map | Output generated by convolution                |
| ReLU        | Activation function                            |
| Pooling     | Reduces feature map dimensions                 |
| Stride      | Number of steps the filter moves               |
| Padding     | Adds extra pixels around the image             |
| Flattening  | Converts 2D data into 1D data                  |
| Epoch       | One complete pass through the training dataset |
| Softmax     | Converts output scores into probabilities      |

## **9. Difference Between CNN and Traditional Neural Network**

| CNN                                             | Traditional Neural Network                    |
| ----------------------------------------------- | --------------------------------------------- |
| Mainly used for image and spatial data          | Used for general numerical data               |
| Uses convolution filters                        | Uses fully connected layers                   |
| Automatically extracts spatial features         | Usually requires feature preparation          |
| Uses fewer connections through local operations | Often has many connections                    |
| Preserves spatial information in early layers   | Does not naturally preserve spatial structure |

## **10. Conclusion**

A Convolutional Neural Network is a powerful deep learning technique used mainly for image processing and recognition. It extracts features using convolution layers, reduces dimensions using pooling layers, and performs classification using fully connected layers. CNN is widely used in computer vision, medical imaging, robotics, and wireless communication.

Important for exams

**Remember these seven main layers in order:**

Input → Convolution → ReLU → Pooling → Flattening → Fully Connected → Output.

**Most important diagrams to practice:**

1. Complete CNN architecture.
2. Convolution operation using a 3 × 3 filter.
3. Max Pooling operation.
4. Flattening operation.

These diagrams and the explanation of each layer are especially useful for a 10- or 13-mark examination answer.
