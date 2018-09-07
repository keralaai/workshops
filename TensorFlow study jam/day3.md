## Neural Networks

- Last class we discussed Supervised Learning,where we fed data to the model and got predictions
- In Supervised Learning,we used a specific algorithm,to process the data
- In the domain of deep learning,we primarily use Neural Network
- In,Neural Networks,we define a task and the network tries to "learn",the function,on it's own 
- A neural network is comprised of many "layers"
- There are three types of layers,input,output and hidden
- The hidden layers are layers,which come in between the input and output
- They are called,"hidden',because,what goes in them,is unknown to us,and we have no role in setting their state
- The dimensionality of these hidden layers represent,the "width" of the model
- Each layer in the Neural Network,consists of "nodes" or also called "units"
- Nodes are linked to each other by a "transition matrix"  
- A "transition matrix,is a matrix of weights,controlling the functions,mapping from layer j to layer j+1 
- Each unit has it's own activation function 
 
<p>
  <img src="Neural_Network.PNG" height="200" width="400" alt="Neural Netwrok"/>
</p>

- Now to compute the cost function,we use a technique called,forward propagation
- We multiply all the nodes with their transition matrices and feed it as input to the node of the next layer 
- After getting the value for each node,we apply the activation function,on it 
- This keeps propagating forward through the layers untl it reaches the output layer
- At the output layer,the neural network learns a function,called the hypothesis function,which is used to determine the output
- What makes Neural Networks different from other methods of Machine Learning is that,we cannot determine which "features" the model learns
- We can only change the task and hyperparameters,keep iterating to get the best result 


<p>
  <img src="FP_1.png" height="200" width="400" alt="Forward Propagation" />
</p>

## Backpropagation 
- Now that we have computed the cost function,we need an algorithm to minimise it
- Our old friend Gradient Descent will not work here,we need a new algorithm
- We need a new algorithm,this is where,Backpropagation comes in,it works similar to gradient descent by minimising the cost function 
- As the name suggests,backpropagation works in reverse compared to forward propagation 
- The intution behind Backpropagation is to calculate the error of node "j",in layer "l" 
- So we are going to capture the error of activation of each node 
- We assign each error ,for each node to a new variable and then calculate the gradient with respect to the cost function
- After minimising the cost function,we update it

