# Development of the NN Prediction Model for the sale price.
According to the given dataset, we have identified four input features, namely GarageCars, GarageArea, OverallQual, GrLivArea, and one output feature that will be forecasted, which is SalePrice. The neural network model is developed using Google Colab, and the language is Python. The main steps followed during the development are mentioned below:
1.	Import the Pandas library and read the .xls file.
2.	The output data frame is assigned to a variable y, and all the input data frame is assigned to a variable x.
3.	The train and test data are split into 80% and 20% of the given dataset, respectively.
4.	The sequential function is used and imported from the keras.models library and the Dense & Activation functions are used and are imported from keras.layers library.
5.	Here the Output of the Sequential function is assigned to bmodel.
6.	By using .add ( ), the hidden layers are added to the model, and the dense function is given as an argument to the add function.
7.	The first hidden layer is provided with the input_dim = 4 (as we have four input features) as the parameter to the dense function. The second and third layers do not require the input_dim as this model follows the sequential order. Keeping in mind that the last layer is considered the output layer, where the dense function has ‘1’ as the parameter.
8.	In the next step, .compile( ) is used for optimizing weights in the neural network. The Optimization algorithm and loss function are passed as parameters to .compile( ), where optimizer = ‘Adam’ and loss = ‘mean_squared_error’.
9.	In .fit( ), the x_train, y_train and epochs are passed as the parameters.
10.	After all the iterations and execution of .fit( ), the value is predicted using  .predict( ).
11.	Further, the Numpy library is imported to compute the error calculations.

# Rationalization of the NN Prediction Model
The rationalization technique is conducted in the given case by keeping four primary factors: the number of hidden layers, neurons, epochs and activation functions. For the development of the model, the probable combinations were first validated, where a minimum of two layers and a maximum of three hidden layers were used. The range of neurons was selected between 16 to 256; the activation functions chosen were tanh, relu & sigmoid. Lastly, the number of epochs was 10000, 15000, & 20000.
As per Table 1, 24 models were tested with the respective hidden layers, neurons, activation functions and epochs. The activation functions, tanh and sigmoid, were eliminated due to high errors for the predicted value, and the relu activation function was considered for further testing.

<img width="350" alt="image" src="https://github.com/Rajdeep096/Neural-Network-NN-prediction-model-for-the-sale-price./assets/147287417/d9cd0a11-a788-430d-8ba9-0619070f8c0b">

# Selected NN Predicted Model
According to Table 1, the highlighted model number 5, which has two hidden layers and 32 neurons each, relu as an activation function and keeping 15000 as the number of epochs, generated an error – APE.mean ( ) = 15.25%.

# Impact of Variables
First, the mean value of each parameter is derived to determine the impact of the parameters on the SalesPrice. Then, the SalesPrice was predicted by keeping one parameter as a variable, and the rest three parameters were the mean values of the respective inputs. Thereafter, the graphs were plotted for all respective inputs with the mean values on the predicted values of the SalesPrice as shown in Figures 1, 2, 3 and 4.
As per Figures 1, 2, 3 and 4, it is clearly observed that keeping the parameter GrLivArea as variables and the other three parameters constant (mean values of the input) has a significant impact on the SalesPrice compared to Overall Quality, Garage Area and Garage Cars.

<img width="258" alt="image" src="https://github.com/Rajdeep096/Neural-Network-NN-prediction-model-for-the-sale-price./assets/147287417/33df5cea-67a7-4356-ad62-28425d88fa32">
<img width="251" alt="image" src="https://github.com/Rajdeep096/Neural-Network-NN-prediction-model-for-the-sale-price./assets/147287417/da543730-dce5-433b-a435-c9132ced0d7c">
<img width="293" alt="image" src="https://github.com/Rajdeep096/Neural-Network-NN-prediction-model-for-the-sale-price./assets/147287417/a2305128-cac3-41d8-afca-6114e5d92108">
<img width="308" alt="image" src="https://github.com/Rajdeep096/Neural-Network-NN-prediction-model-for-the-sale-price./assets/147287417/fd31a449-3ff7-4938-bdee-1907c227c225">

# Forecasted Value
As per the given data, Garage Cars = 2, Garage Area = 600 ft2, Overall Quality = 7, and Ground Living Area = 2,200 ft2.
The forecasted value of SalePrice is $235,481.5 based on the information provided, which accounts for four factors: Garage Cars, Garage area, overall quality, and Ground living area. Various combinations of epochs, hidden layers, neurons, and activation functions were applied to a model trained on a given dataset to arrive at the predicted value. However, observing that the model still requires development is essential, as the error rate is 15.25%.
This indicates that the predicted value may differ from the actual value by up to 15.25%, which can significantly impact the prediction's accuracy. Therefore, additional model and feature selection refinement may be required to enhance the accuracy of the predicted SalePrice.

# Activation Functions in the Neural Network
Incorporating nonlinearity into a model requires using a mathematical function known as an activation function. This function is applied to the output of each neuron in a neural network. This nonlinearity is essential because it allows neural networks to uncover complicated, nonlinear correlations between inputs and outputs, which is one of the primary goals of neural networks. Neural networks may, however, learn substantially more complicated correlations between inputs and outputs and achieve better accuracy over a broad spectrum of tasks if they use nonlinear activation functions such as the sigmoid, ReLU, or tanh functions. These functions are examples of nonlinear activation functions. 

The various activation functions each have unique attributes and may be better suited to specific categories of responsibilities. For example, the ReLU function is extensively used for picture recognition tasks since it is computationally efficient and often performs well with big datasets. On the other hand, the sigmoid function is widely used in jobs involving binary classification since it produces probabilities that may be read as values that fall between 0 and 1. The tanh function is a nonlinear activation function that, like the sigmoid function, compresses its input into the range of -1 to 1. The selection of an activation function is an essential part of the process of designing neural networks, and it has the potential to significantly impact the effectiveness of these networks 

# Limitations of the Chosen Model
1.	It is important to note that the model must still be developed since the error rate is 15.25%. This suggests that the anticipated value might deviate from the actual number by up to 15.25%, which could significantly influence the forecast's accuracy. Therefore, more model and feature selection refinement may be needed to improve the anticipated SalePrice's accuracy.
2.	High-quality data is necessary for neural networks to learn meaningful patterns and correlations. Neural networks may overfit or underfit the training data if there is insufficient data, which can negatively affect their performance on fresh data.
3.	Because neural networks are black boxes that translate inputs into outputs, they may be challenging to understand. This lack of interpretability might make comprehending how the model generates its predictions challenging, which can be problematic. Although neural networks offer numerous advantages, it is crucial to consider their drawbacks and possible difficulties when building and implementing them in practical applications.







