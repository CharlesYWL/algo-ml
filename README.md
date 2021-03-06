# Report - Nerual Network on Handwritten Digits

### Preparation
- Data has size (5000, 400). 5000 samples, each has 400 features. Output into 10 classes
- Using architecture [400, 25, 10]. Input layer 400 elements; one hidden layer with 25 elements; output layer 10 elements
- Plan 3 runs. Run 1: optimize sample number, decide bias vs. variance. Run 2: optimize regulating rate. Run 3: compute Theta and test on test data set

### Analysis Before Run 1
- Each data has 400 features, which is absolutely enough for human beings to classify the data. Thus we consider this is a feature-rich data and we have high chance running into high-variance (overfitting) result. High regulating rate (lambda) might help.
- If it's a high-variance case, the best option for us is to use more samples and apply high regulating rate (lambda).
- We firstly run sample number [2000, 3000], if we see converge, we take the most optimized sample number in that range. Otherwise, we need to run sample number [1, 1000] to make sure of converge.
- If it's a high-variance case, we hope to see the plot like below. 
	- Cross validation curve (cv) and training curve (train) never go across. 
	- Difference between cv and train is getting smaller as sample increases
	- Relatively high cv cost and low train cost  
	![high_variance](https://github.com/TrentaIcedCoffee/algo-ml/blob/master/readme_resource/high_variance.png)

### Run 1 
#### sample number [1, 1000]
#### sample number [2000, 3000] (max iteration 400, 1001 runs, takes 2.23 hours)
- Most optimized sample number is 2989.
- We see cv and train doesn't go across
- We fail to see cv and train converge.
- Cv and train have similar and low cost.
- We need to run sample number [1, 1000] to see if cv and train converge.  
![run1_2000_3000](https://github.com/TrentaIcedCoffee/algo-ml/blob/master/readme_resource/run1_2000_3000.jpg) 
