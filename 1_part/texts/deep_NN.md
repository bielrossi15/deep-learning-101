# DEEP NEURAL NETWORK

**Logistic regression** -> shallow
**2 layer NN** -> not so shallow
**5 layer NN** -> deep

**Early layers detect simple things, like edges in a photo, and then final layers put together the information, thats why we use deep neural networks**

**DEEP NEURAL NETWORK HAVE MORE LAYERS**

<NOTATION>

- L = number of layers 
- n[l] = units in layer l (n[0] = nx 
- a[l] = activations in layer l 
- a[l] = g[l](z[l]) (a[0] = x) 
- W[l] = weights for z[l] 

X : Z[1] = W[1]x + b[1]
    A[1] = g[1](Z[1])
    Z[2] = W[2]A[1] + b[2]
    A[2] = g[2](Z[2])
    ...
    Z[L] = W[L]A[L - 1] + b[L]
    A[L] = g[L](Z[l]) 


# MATRIX DIMENSIONS

- Z[l] = dZ[l] = matrix(n[l], n[m])
- X = A[0] = matrix(n[0], m)
- A[l] = dA[l] = matrix(n[l], m)
- W[l] = dW[l] = matrix(n[l], n[l-1])
- b[l] = db[l] = matrix(n[l], 1)


# PARAMETERS AND HYPERPARAMETERS

- Parameters: W[1], b[1], etc
- Hyperparameters: learning rate,    iterations, hidden layers, hidden units, activation function


**HYPERPARAMETERS = PARAMETERS THAT CONTROL W AND b, VALUES THAT DETERMINE VALUES OF W AND b**	








	
