# MICN
A multi-scale branch structure to combine local features and global correlations to capture the overall view of time series.

# MICN Implementation
In this project we reimplemented the original paper MICN: Multi-Scale Local and Global Context Modeling for Long-Term Series Forecasting.

The authors aimed to overcome the limitations of Transformer-based methods in long-term series forecasting, particularly their high computational complexity for global correlations and inadequate local feature modeling.

To address these issues, they introduced the Multi-Scale Isometric Convolution Network (**MICN**), which integrates local feature extraction with global correlation modeling. This approach, leveraging *convolutional operations*, offers enhanced accuracy and efficiency compared to traditional *Transformers* methods.

Key outcomes of this implementation include:
- Achieving linear computational complexity by using a convolution-based structure instead of the self-attention mechanism.
- Developing a local-global architecture for effective extraction and aggregation of information and patterns, surpassing the performance of self-attention mechanisms in long-term dependency modeling.

Through the notebook file *MICN.pynb* we provide a detailed, step-by-step explanation of each code block implementation.

# How to run the code
Before running the notebook, it is necessary to load the datasets on which you want to train the model. All the datasets used were placed in the *datasets* folder of this repo. So, you need first to upload the dataset into the notebook. <br> 

After, in the *Training code* paragraph of the notebook, all the hyper-parameters are set, including auxiliary variables such as the name of the dataset that you want to use as input. <br>
Also, you can choose the *prediction lenght* or whether to use a *mean* or *regression* to predict the trend of the series. <br>

However, the paragraph in the notebook provides a clear indication on the possible settings of these parameters.

# Results
In the following, we will show the results obtained from the paper author's model and compare them with the results obtained from our reimplemented model. Specifically, for each of the datasets we performed 3 tests, since there is randomness during the training process (e.g. due to the shuffling applied by the dataloader or from the initialization to random values of some weights). The numbers we have included in the table below, derived from the average of the values obtained from the 3 tests.<br>

Some tests were performed locally through a NVIDIA RTX 3050 Ti 4GB GPU. Other tests, due to the limited memory of the video card, were performed on Google Colab with an NVIDIA T4 GPU provided by Colab. <br>

Some types of tests, i.e., those involving datasets with very large and with more than 800 features or with a prediction length of 720, we were unable to perform the training because of lack of computational power of the GPU, or because of the time it would have been necessary to keep the Colab session active. We marked them in the table with *'---'* signature. <br>

As we can see from the table below, we were able to obtain results very close to those presented in the paper. The table on the left represents the results of the original paper, while the table on the right represents the results of our model. <br>

![Results](https://github.com/Awenega/MICN/blob/main/images/results.png?raw=true)
