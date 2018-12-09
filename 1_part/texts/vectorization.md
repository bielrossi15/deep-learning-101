# VECTORIZATION

' to compute non-vectorized wT * x '

z = 0
for i in range(n - x):
	z += w[i] * x[i]
z += b

' vectorizing it '

z = np.dot(w, x) + b

GPU -> PARALLELIZATION INSTRUCTIONS SIMD (SINGLE INSTRUCTION MULTIPLE DATA)
CPU -> SIMD, so using functions like np.dot(), you let numpy do the function without the for loop, taking better advantage of parallelism

## SO, WHENEVER POSSIBLE, AVOID EXPLICIT FOR LOOPS

x -> a[2] = y_hat
x(1) -> a[2](1) = y_hat(1)
x(2) -> a[2](2) = y_hat(2)
x(3) -> a[2](3) = y_hat(3)
.
.
.
x(m) -> a[2](m) = y_hat(m)



< CODE UNVECTORIZED
for i = 1 to m:
 
 z[1](i) = W[1]*x(i) + b[1]
 a[1](i) = sigmoid(z[1](i)) 
 
 z[2](i) = W[2]*a[1](i) + b[2]
 a[2](i) = sigmoid(z[2](i)) 
>

< VECTORIZED CODE

 Z[1] = W[1]*X + b[1]
 A[1] = sigmoid(Z[1]) 

 Z[2] = W[2]*A[1] + b[2]
 A[2] = sigmoid(Z[2])
>



A is the matrix with a[](i) values

<------> in a, this direction is trainig examples, and the other is your hidden units
 


 












