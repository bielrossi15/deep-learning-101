# TensorFlow basics

**Tensorflow steps**
- create tensors (variables)
- write operations
- initialize tensors
- create session
- run the session

**Variables**
- you can create constants by writing = tf.constant(number, name='constant1')
- the same goes for a variable = tf.Variable(variable_value, name'variable1')
- and placeholders too (objects that you can specify the value later) = tf.placeholder(tf.int64, name='placeholder1')
- you can initialize a placeholder when running your sessions using a feed dictionary (feed_dict)
- to initialize your variables, just assign a variable to tf.global_variables_initializer()

**Operations**
- you can use operations like tf.add() to add values or tf.matmul() to multiply 2 matrices, etc

**Session**
- the session is where you will run your operations
- you create a session by assign sess = tf.Session()
- you run a session by writing sess.run(some_operation)
- after this, you can close your session with sess.close()
- the other way is to create a local variable 'with tf.Session() as sess:' so you wont need to close
