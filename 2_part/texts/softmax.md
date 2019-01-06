# Softmax

**Non binary classification**
- C = number of classes
- the last layer will have the probability of each one of the classes, so y^ will have (C, 1) shape
- the unusual thing is that the input is a vector, and the output too, different from the other ones like sigmoid and relu

**How to write**
- in the last layer L you will compute: z[L] = w[L] * a[L - 1] + b[L] 
- we will compute a variable elementwise: t = e ** z[L] (C, 1)
- and for the activation function will be a[L] = ti/(sum ti)

**Why it works?**
- lets say you have a vector z[L] = [5, 2, -1, 3]
- t = [e ** 5, e ** 2, e ** -1, e ** 3] = [148.4, 7.4, 0.4, 20.1]
- sum ti =  176.3
- a[L] = t/176.3 
- so your values divided will be [0.842, 0.042, 0.002, 0.114], so this is your probabilities, that add up to 1

**Training softmax classifier**
- your loss function in a softmax classifier, is normally - sum yi log y_hat i
