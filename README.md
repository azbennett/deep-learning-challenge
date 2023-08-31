# deep-learning-challenge
# Steve Bennett

# Overview: 
* I was tasked to design a tool to predict with a binary classifier whether applicants will be successful if funded by Alphabet Soup.
* It used a CSV file containing over 30,000 entries 
* I then preprocessed the data and used it to compile, train and evaluate the 4 different models.  

# Results:
* Despite my best efforts I was never able to exceced the 73% accurate rating through multiple optimization trials.

* All attempts used the target variable of IS_SUCCESSFUL as the y value (target), and the remaining columns as the X value (features).

* Initially I started with 3 hidden layers (AlphabetSoupCharity.ipynb), no batch size, and 100 epochs.  This was part of the initial 72.48% accuracy value.
* I attempted the base 2 columns dropped of EIN and Name with 100 epochs. Resulting in a 72.xx% result.

* Then I expanded out dropping Status, Income_Amt, and even Special_Considerations columns from the features list - netting the same 72.xx% results within a few tenths of a percent.

* During my multiple attempted optimization methods I tried to further adjust by changing batch sizes, epoch sizes, and additional hidden layers did not help push the levels of 75% that we were tasked with. These still resulted with values in the mid to high 72.xx% area.

* Lastly I attempted using elu and sigmoid activation methods for my hidden layers - still not hitting the 73 or higher goals.

# Starting Result (AlphabetSoupCharity.ipynb) - 2 dropped ('EIN', 'NAME', 'STATUS'), 100 epoch, 72.48% acc
# Optimization (AlphabetSoupCharity_Optimized.ipynb) 
# Initial optimization - 5 dropped ('EIN', 'NAME', 'STATUS', 'INCOME_AMT', 'SPECIAL_CONSIDERATIONS'), 5 hidden layers [2000,1000,500,250,125], 200 batch, 100 epoch - 72.93%.
# Trial 1 - Same 5 dropped, 4 hidden layers 250 each, same batch and epoch - 72.73%
# Trial 2 - 5 hidden layers 250 each, 50 batch, 100 epoch - 72.87%
# Trial 3 - Same 2 - used sigmoid instead of relu - 73.00% - the highest one of all.

# Summary:
* I ended up trying 7+ different methods - all of which could not hit the 75% target goal.  This ended up being a very difficult assignment as  there were so many different variables and possibilities.   It is possible that supervised learning or forest models may be better at this task?


# additional notes - trials used:
* Additional trials used:

* Dropping SPECIAL_CONSIDERATIONS and using: number_input_features = len(X_train[0]) hidden_nodes_layer1 = 500 hidden_nodes_layer2 = 250 hidden_nodes_layer3 = 125 hidden_nodes_layer4 = 65 resulted in 72.5947%

* Not dropping anything and then Using: number_input_features = len(X_train[0]) hidden_nodes_layer1 = 500 hidden_nodes_layer2 = 250 hidden_nodes_layer3 = 125 hidden_nodes_layer4 = 65 resulted in 72.501456%

* Batch 50, epoch 150 and number_input_features = len(X_train[0]) hidden_nodes_layer1 = 500 hidden_nodes_layer2 = 250 hidden_nodes_layer3 = 125 hidden_nodes_layer4 = 65 resulted in 72.61807%

* Even adjusting the batch, epochs, and/or more hidden layers I cannot peak over 75% accuracy.

* I tried removing status, removing special_conditions. No help.

* Tried smaller and larger batch sizes, more and less epochs.

* Tried changing relu to elu.

* Nothing helps. I am at a loss as to what can help break 75%.

* Tried dropping MANY more columns, adjusted a longer epoch. Still stuck in the 72-73% zone