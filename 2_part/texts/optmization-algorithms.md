# OPTIMIZATION ALGORITHMS


## Mini-batch gradient descent
- You get mini-batches (divide your X and Y
into some parts)
- X{1}, X{2}, ...X{n} and Y{1}, Y{2}, ...Y{n}
- Mini-batch t: X{t}, Y{t} (dimension = (nx, size of your mini-batch))
- If you pass only one time in your entire training set, you have run **1 EPOCH**
- You need to chose your mini-batch size bigger than 1 and smaller than m, to make it less noisy and faster
- If m <= 2000, use m
- Else -> use your mini batch as a power of 2 (64, 128, 256, 512)


## Exponentially weighted averages
- Initialize V0 = 0
- Vt = 0.9 * Vt-1 + 0.1 * Qt
- Vt = B * Vt-1 + (1 - B) * Qt
- Higher B, smoother curve but slower, because it gives higher weight to Vt-1 and smaller weight Qt
- To see in wich size its averaging over, you use the formula 1/(1 - B) 
- To make your values weighted when started, you can use bias correction =  Vt/(1 - B ** t)


## Gradient descent with momentum
- Almost always is better than gradient descent
- You want the learning in Y to be slower, and in X be faster, to not diverge
- Compute dW, db on current mini batch:
	Vdw = B * Vdw + (1 - B) * dW
	Vdb = B * Vdb + (1 - B) * db

	w := w - alpha * Vdw
	b := b - alpha * Vdb
- This makes your average in Y be closer to zero, and your X will be larger, makes the path of your algorithm be straight forward, iso you can increase alpha
- dW = acceleration, Vdw = velocity and B = friction
- Most comum value of B is 0.9 (average size of averaging equals 10)


## RMSprop	
- Sdw = B * Sdw + (1 - B) * dw ** 2
- Sdb = B * Sdb + (1 - B) * db ** 2
- w := w - alpha * (dw/sqrt(Sdw))
- b := b - alpha * (db/sqrt(Sdb))
- db ** 2 will be larger than dW ** 2, so your w in horizontal direction will be larger, and your vertical b will be smaller, because it will divide by Sdw and Sdb

## Adam optimization algorithm
- Momentum + RMSprop
- Vdw = Sdw = Vdb = Sdb = 0
- Vdw = B1 * Vdw + (1 - B1) * dW, Vdb = B * Vdb + (1 - B) * db
- Sdw = B2 * Sdw + (1 - B2) * dw ** 2, Sdb = B * Sdb + (1 - B2) * db ** 2
- last, you implement bias correction
- Vdw = Vdw/(1 - B1 ** t), same to Vdb
- Sdw = Sdw/(1 - B2 ** t), same to Sdb
- w := w - alpha * (Vdw_corrected/sqrt(Sdw_corrected) + eps), same to b

**Hyperparameters**
- alpha -> need to tune
- B1 -> normally 0.9 (dw)
- B2 -> normally 0.999 (dw ** 2)
- eps -> 10 ** -8

**Meaning**
- Adam means adaptive moment estimation















