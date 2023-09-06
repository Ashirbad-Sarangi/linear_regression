# Linear Regression

			       Linear Regression


Linear Regression is a method which is extensively used in the field of machine learning in training a model to generate a linear equation using the attributes and coefficients based on the data fed to model. This model is supervised by the outputs of the data. Linear Regression basically regresses i.e. goes from the outputs to find weights and then produces the values through which the coefficients are found. The output of the model is checked through the performance measures like MSE, RMSE etc. methods where the predictions are compared with the actual output and the results. The performance measures show to which degree is the model dependable and what is the margin of error for the performance. In lay man terms, linear regression is a method through which a linear equation is built from the data with the attributes as variables.Due to the large amount of data present, the weights or the co-efficients of the variables are found out.

				 Specifications
In this repo, there is a class of linear of regression built from scratch. The library used are :
[-] pandas : to read the dataframes
[-] numpy : to perform the matrix calculations
[-] matplotlib : to plot the graphs

				  Description
The generalised class of the linear regression has certain variables and functions to make the work easier.

Variables
    =========
        N              # Number of datapoints in the dataset
        n              # Number of attributes in the dataset
        maxima         # To store the maxima of each attribute of the training set
        minima         # To store the minima of each attribute of the testing set
        sgd            # To run Stochastic Gradient Descent or not
        plot_rmse      # To plot the RMSE graph or not
        plot_metrics   # To plot the metrics asked in the Assignment questions or not
        alpha          # The optimal hyperparameter
        df_data        # The preprocessed complete dataset
        w_star         # Optimal Weights selected


    Functions
    =========
        load_data( path )     
        # Reads the data from the path and Preprocesses it

        preprocess_data()   
        # Pre-Process the data by Appending x0 column of 1s , Replacing Null values with 0 etc.

        normalise_data( df )  
        # Normalise the data using Min-Max method

        rmse( y , y_hat )       
        # RMSE between Actual Output and Predicted Output

        cost( y , y_hat )       
        # Find the cost associated with the current parameter

        optimal_weight( df )  
        # Use the function to find the optimal weights using different values of alphas and a option with the user to select from either batch gradient method or stochastic gradient method. Aditionally, all the metrics required such as cost vs iteration, cost vs weights, hyperplane etc. will be plotted using this function according to the users requirement. This function basically checks whether the w found either through batch or stochastic gradient converges or not i.e. whether it is less than epsilon

        batch_gradient_descent( w_star , df , alpha ) 
        # Training the weights after each epoch is batch gradient descent

        stochastic_gradient_descent( w_star , df , alpha ) 
        # Training the weights within each epoch is stochastic gradient descent

        monte_carlo( alphas , k , training_perc ) 
        # Running the optimal weight function k times for cross validating the data fit in Linear Gradient also through this method, optimal alpha from a series of alpha is found such that the alpha has the least avg rmse in all the iterations
        
        plot_required_metrics(self,errors, costs, weights,w_star)   
        # According to the question all the metrics that were needed to be plotted are plotted in this function

        train( df_train , sgd = True , plot_rmse = True , plot_metrics = True )
        # Train the data for the chosen alpha, with an option to whether to use sgd , plot the rmse, question metrics etc."

        test( df_test )
        # Predict the output through the learnt w_star and check its performance error

        split_data():
        # Splits the whole dataset into Training and Testing set. Returns df_train and df_test


    Sequence of Function Calls 
    ===========================
        # load_data( path )
        # monte_carlo( alphas , k , training_perc )
        # training_set , testing_set = split_data()
        # train( training_set , sgd , plot_rmse , plot_metrics )
        # test


 
