# NEURAL NETWORK

**New notation**

< z[1] = w[1]x + b >

< the new [] is to show layers, that are different nodes alligned >

**How we will compute now**
< instead of only one z and a calculation, we will compute as many layers as we have, and after we will compute the Loss function >

< x1, x2,... > -> **INPUT LAYER**
< multiple nodes layer > -> **Hidden layer**
< single last node > -> **Output layer**
< y_hat > -> **Predicted value**

**Hidde layer** -> < You dont see it in the training set >

< a[0] = X = activation feature of the input layer, that pass the value X to the hidden layer >

< a[1] = hidden layer, each node being a[1]1, a[1]2, etc, being as long as many layers you have >

< a[2] is your single last node, that is your y_hat >

**a[l]i, l = layer, i = node in layer**

< SO >


z[1] = matrix(nodes, inputs) W * X + matrix(nodes, 1)b = 
		|  z[1]1  |
		|  z[1]2  |
		|   ...   |
		|   ...	  |
		|z[1]nodes| nodes x 1



a[1] =				= sigmoid(z[1])
 		
		|  a[1]1  |
		|  a[1]2  |
		|   ...   |
		|   ...	  |
		|a[1]nodes| nodes x 1


# COST FUNCTIONS

paramns: w[1] (n, n-1), b[1] (n, 1), w[2] (n, n-1), b[2] (n, 1)

J(w[1], b[1], w[2], b[2]) = (1/m) Sum L(y_hat, y)

# GRADIENT DESCENT

Repeat {
  < compute predictions(y_hat(1), ..., m) >

< dw[1] = dJ/dw[1], db[1] = dJ/db[1], .... >

< w[1] = w[1] - alpha * dw[1]

  b[1] = b[1] - alpha * db[1]

  etc
>

}


# FORWARD PROP FUNCTIONS

Z[1] = W[1] dot X + b[1]
A[1] = g(Z[1])

Z[2] = W[2] dot A[1] + b[2]
A[2] = g(Z[2])

# BACK PROP FUNCTIONS (FOR GRADIENT DESCENT)

**Second layer**
< dZ[2] = A - Y
  dW[2] = dZ[2] * a[1].T * (1/m)
  dB[2] += dZ[2] * (1/m)
>

**First layer**

< dZ[1] = W[2].T * dZ[2] * g'(Z[1])
  dW[1] = dZ[1] * X.T * (1/m)
  dB[1] += dZ[1] * (1/m)
>

 


















