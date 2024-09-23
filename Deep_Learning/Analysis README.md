# deep-learning-challenge
Homework 21

Overview of the analysis: Explain the purpose of this analysis.

create a tool for Alphabet Soup to help select successful venture applicants for funding. Use features in the 34,000 organization dataset that have already received funding throughout the years and to to predict the success accuracy of these applicants with a minimum of 75% accuracy prediction.

Data Processing:
    1. What variable(s) are the target(s) for your model?  IS_SUCCESSFUL
    2. What variable(s) are the features for your model? Examples of feature variables are APPLICATION_TYPE and CLASSIFICATION.  They are the other variables in the dataset that weren't dropped in earlier processing.
    3. What variable(s) should be removed from the input data because they are neither targets nor features?  The name and EIN were removed
    4. Also did some cleanup of combining data in to other category for classification, application type, use case and organization.

Compiling, Training, and Evaluating the Model:
    1. How many neurons, layers, and activation functions did you select for your neural network model, and why?  I chose my model 1.  It had quite a bit more accuracy than other models and less loss than some. While the loss was more than my first model, the accuracy went from 53% to 70%.  So even though there was more loss the extreme gain in accuracy was worth it.  I tried more EPOCHS and either the loss increased or there was little change.  Also, the neuron increase/decrease didn't help.

    Neurons = 8
    Layers = 1 hidden layer with 8 neurons
    I chose outer layer with sigmoid activation


    # Create the Keras Sequential model.  I also tried with one layer, 2 layers and added even more layers without improvement in order to reach 75%.  At the bottom of the Notebook there are also other things I tried (TANH, LeakyRelu)
    nn1 = tf.keras.models.Sequential()

    # Add our first Dense layer, including the input layer
    nn1.add(tf.keras.layers.Dense(units=8, activation="relu", input_dim=len(X.columns)))

    # Add the output layer that uses a probability activation function
    nn1.add(tf.keras.layers.Dense(units=1, activation="sigmoid"))

    # Check the structure of the Sequential model
    nn1.summary()


    RESULTS:
    Loss: 1.6681212186813354, Accuracy: 0.704723060131073

    2. Were you able to achieve the target model performance? No
    3. What steps did you take in your attempts to increase model performance?  Added Neurons, Layers, Epochs, Adjusted Neurons in each layer, tried TANH without expectation of a better result over RELU, which was the case, tried leakyrelu.


Summary of the overall results of the deep learning model. Include a recommendation for how a different model could solve this classification problem, and then explain your recommendation.

Using Relu, Tanh, Leaky Relu didn't achieve a 75% accuracy.  Perhaps the use of other models from Unit 21 may work better vs the deep learning models.  Or, we could continue to try increasing neurons to possibly 32 to see if more complex patterns are found while playing with the neurons in other layers. 

