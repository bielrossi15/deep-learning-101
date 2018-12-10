# BYNARY CLASSIFICATION (Y = 0 OR 1)

Given X, want Y

y^ = P(y = 1 | x) probability of y being 1 given x

Parameters = w (n dimension vector), b (real num)

Output y^ = wTranspose x + b doesn't work, because this is a linear regression function, meaning it can be much bigger than 1 or lower than 0

**SO WE USE**

## LINEAR REGRESSION MODEL

**z = wTx + b**

<- we use wTransposed because m its a (nx1) matrix and x is a (nx1) matrix and we want to multiply x times the weight to make a linear transformation and get the output = (1x1), so we transpose it to make this multiplication ->

<- then we sum it with the bias to shifts the decision boundary away from the origin ->

<- after, we use sigmoid function to make values probabilistically plausible, meaning they will be between 0 and 1 ->
**σ = sigmoid** 

**σ(z) = 1/(1 + e^-z)** 
if z -> inf sig tends to 1
if z -> -inf sig tends to 0

**y^ = σ(z)** 

## LINEAR REGRESSION LOSS FUNCTION (SINGLE TRAINING EXAMPLE)

**i = X vector column, your feature matrix**
**yi^ = σ(wTxi + b)**

**Loss(y^, y) = - (y log y^ + (1-y) log(1 - y^))**
< -we want it to be small as possible ->

- if y = 1, L(y^, y) = -log y^ <- you want y^ to be large, you want log y^ to be large, so it needs to be as close as possible to 1 ->

- if y = 0, L(y^, y) = -log(1 - y^) <- you want y^ to be as small, you want log (1-y^) to be large, so it needs to be as close as possible to 0 ->

## LINEAR REGRESSION COST FUNCTION (ENTIRE TRAINING SET)

**J(w, b) = (1/m)Sum(L(yi^, yi)) =**
**-(1/m) SUM (yi log yi^ + (1-yi) log(1 - yi^))**
 <- The average of your Loss function, so you need to find the parameters w and b to minimize your overall cost, meaning that yi^ must be as close as possible to your desired value (y being 1 or 0) ->


## GRADIENT DESCENT

- Find w and b to minimize J(w, b), wich is a convex function 

- alpha = learning rate, control our step size 
dw  = change at the parameter w 

FOR J(w), a two dimensional plot

**Repeat { w := w - alpha * dJ(w)/dw }**
<IN CODE>
**w := w - alpha dw**
< So if your w is higher than the optimun point, it subtracts by your alpha times your rate of change, until your derivative is zero (optima) >

<FOR J(w, b), a 3 dimensional plot>
**w := w - alpha * dJ(w, b)/dw**
<and>
**b := b - alpha * dJ(w, b)/db**
**Its good to normalize your vector, because computes your gradient faster (vector/||vector||)**

## COMPUTING GRADIENT DESCENT

- given x1 and x2 >
**z = w1x1 + b**
-> **y^ = a = σ(z)** -> **L(a, y)**

< so you do your backwards derivatives >

- first, you need to compute derivatives of your loss/a >
**da = dL/da = -((y/a) - (1-y)/(1 - a))**
- after, you need to compute your derivative of your loss/z >
**dz = dL/dz = dL/da * da/dz = (a - y)**
- finally, you calculate your derivative of your loss/wi >
**dL/dw1 = dw1 = x1 * dz and db = dz**

- SO, ALL YOU NEED TO DO IS CALCULATE DZ = A - Y AND DW1 = X1 * DZ >
 and your gradient descent updates are 
**w1 = w1 - alpha * dw1**
**b = b - alpha * db**

## GENERAL CODE EXAMPLE 

	dw = np.zeros((n - x), 0)
	for i = 1 to m:
		zi = wT * xi + b
		ai = σ(zi)
		J += -(yi * log ai + (1 - yi) * log (1 - ai))
		dz = ai - yi
		dw += xi * dz
		db += dzi

	 J /= m
	 dw1 /= m
	 dw2 /= m
	 db /= m
	 w := w - alpha * dw
	 b = b - alpha * db 

















