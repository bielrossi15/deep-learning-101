#REGULARIZATION

**If you have been experiencing overfitting and you cant add more training data**

#Methods

##Frobenius norm (called weight decay)
- J(w[1], b[1]..., w[l], b[l]) + (reg_parameter/2m)*SUM norm(w[l] ** 2)
- norm ** 2 -> SUM SUM wij ** wij = wT*w 
- dw[l] = (back prop) + (reg_parameter/m) * w[l]
- w[l] = w[l] - alpha * (reg_parameter/m) * w[l] - alpha(back prop) 

< Regularization parameter >
- regularization parameter
- represented by lambda


##Dropout regularization
- Creating a probability to delete nodes
- keep_prop = probability of a node being kept
- d3 = np.random.rand(a3.shape[0], a3.shape[1]) < keep_prop
- a3 = np.multiply(a3, d3) #number by number multiplication
- a3 /= keep_prob #to make the matrix a3 not change the expected value of z4 = w4 * a3 + b4
- Ate test time, you dont use dropout
- It will need to spread out the weights, so te squared norm will be reduced
- Downside = J(w, b) is not well defined

##Data augmentation
- Lets say you have pictures in your training set
- You can crop them, change a few things and have more data
- Is worse than getting different data, but it's easier

##Early stopping
- Plot training and dev sets errors
- So you stop halfway, and you get a midsize ||w||frobenius
- Downside = you mix overfitting problem and optimizing J(w, b), so you dont get J(w, b) at the best optimization


##Why reg. prevents overfitting?

- Making a NN simples
- If lambda is large, w[l] becomes closer to 0, meaning it will be more like a linear function, making it less able to overfit
