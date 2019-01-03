# Hyperparameters

**Names**
- learning rate (alpha)
- beta
- beta 1, beta 2, epsilon
- number of layers
- number of hidden units  
- learning rate decay?
- mini batch size

**How to chose**
- chose random points (why? because if you chose grid values and you will chose values for alpha and epsilon, your alpha value will matter too much, and your epsilon wont matter at all, so you will try MxN matrix, but actually, you'll only try 5 values for alpha, so if you chose random values, you will actually try 25 different alpha values)
- so chose random, not grid
- coarse to fine (find a region that your points are working the best, and focus on that smaller region, making a more dense sample)

**Picking values at random**
- the number of hidden units are a reasonable value to pick at random, you choose a range of value and try a random value
- the number of layers maybe randomized or make a grade search

**Hyperparameters scale**
- if you choose to try between 0.001 and 1, dont focus on the range of 0.1 and 1, instead try to scale between powers of 10
- r = - 4 * np.random.rand() and alpha = 10 ** r (log scale)

