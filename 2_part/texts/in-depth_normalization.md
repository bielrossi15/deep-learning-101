# Batch normalization


**Batch normalization pros**
- make NN more robust 
- makes hyperparameter search much easier
- more range to choose the hyperparameters

**How to do**
- the most commom thing to do is to normalize your pre-activation function, but you can normalize your activation function too
- you calculate the mean and the variance of your z[i] values
- after you do z(i)normalized = (z(i) - media)/sqrt(variance + eps) 
- then you make z~ = gama * z(i)normalized + beta, that are learnable values (just like w and b)
- so if gama = sqrt(variance + eps) and beta = media, than z~ = z, using that equation presented before
- so batch normalization works better because you often normalize the input X, and with batch normalization, you normalize each layer, and you use gama and beta to make your layers values not between 0 and 1, but in a much wider range
- because you will subtract by the mean, you b[i] value will be subtracted too, so you can get rid of it (set it to 0), so you will use your beta value as you new constant

**Computing**
- you compute your value between computing z and a
- x -> z -> z~ -> a (g(z~))
- so your parameters are w[1], b[1], ... and gama[1], beta[1], ...
- can be used with adam, rmsprop, gradient descent and momentum
- using te can implement batch norm with tf.nn.batch_normalization

**BN in mini batches**
- you compute your z~ mini batch by mini batch
- z~ of mini batch x{1} doesn't appears in the mini batch x{2}

**Why batch norm works?**
- normalizing your features to make them between a range of 0 and 1 accelerate the process in a logistic regression NN, so we just extend this first intuition to a complete NN
- coverage shift -> if your input feature shifts, you will need to retrain your whole model, so, in example, a black cat classification will not work well on colored cats classification so batch norm reduces the difference, making the mean and variance to maintain, limiting the amount to wich updating the early layers paramns can affect the distribution of values that deeper layers sees and learn on
- it has a small regularization side effect, adding a little noise in your z values and the computation of z -> z~ , because it computes only in the mini batches and have multiples of noise because it scales by the standard deviation and aditive noise, because subtracts by the standard media, similar to dropout
