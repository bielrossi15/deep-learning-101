# SETUP OPTIMIZATION PROBLEM



## Normalizing training sets
- Speed up training

**2 STEPS**
- Subtract the mean 
 x := x - mean, make the mean = 0

- Normalize variance
 sigma ** 2 = (1/m) SUM x ** 2 (variance of each feature)
 x /= sigma ** 2

- Normalize test set the same way

**Why normalize?**
- If you have x1 : 0... 1000 and x2: 0.... 1
- Your ratio (range of values) of w1 and w2 will be very different, making the cost a less symmetrical function, meaning your gradient descent learning rate will need to be smaller, making your gradient decent steps smaller

## Vanishing and exploding gradients
- Derivatives may be very small or very big
- If w[l] > Id or w[l] < I, activations will increase or decrease exponentialy

**So you need a careful choice of how to initialize your weight**
- Set the variance of wi = 1/n (n = number of features for the neuron)
- w[l] = np.random.randn(shape) * np.sqrt(1 0R 2/n[l - 1])

## Gradient checking

- lim (f(x + eps) - f(x - eps)) / 2eps

**Implementation**
- Take w[1], b[1]... and reshape to theta, so J(w[1], b[1], ...) = J(theta)

- Take dW[1]. db[1], ... and reshape to dTheta

for each i:
	dTheta_aprox[i] = J(theta1, ... theta[i] + eps,...) - (theta1, ... theta[i] - eps,...) / 2eps
	checks ||dTheta_aprox - dTheta||/||dTheta_aprox|| + ||dTheta|| = 10 ** -7

**USE ONLY TO DEBUG**
**DOESNT WORK WITH DROPOUT**



































