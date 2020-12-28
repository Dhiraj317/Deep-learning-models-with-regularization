# Deep-learning-models-with-regularization
**Problem Statement**: You have just been hired as an AI expert by the French Football Corporation. They would like you to recommend positions where
France's goal keeper should kick the ball so that the French team's players can then hit it with their head.

![field_kiank](https://user-images.githubusercontent.com/63168221/103189302-07535f80-489a-11eb-8061-01847ebd6d0f.png)

**Goal**: Use a deep learning model to find the positions on the field where the goalkeeper should kick the ball.

**Step-1: Using Non-regularized model**

<img width="465" alt="model w:o regularization" src="https://user-images.githubusercontent.com/63168221/103189555-2999ad00-489b-11eb-91fe-3da01f6ceae8.png">

This is a baseline model, it achieved only 91% accuracy in testing set. Moreover, the non-regularized model is obviously overfitting the training set. It is fitting the noisy points. In the following steps, we will see how changing to the regularization models improves the accuracy. 


**Step-2: L2-regularization model**

The standard way to avoid overfitting is called L2 regularization. It consists of appropriately modifying the cost function by introducing a hyperparameter and calculating both forward & backward propogation using weight parameters.L2 regularization relies on the assumption that a model with small weights is simpler than a model with large weights. Thus, by penalizing the square
values of the weights in the cost function one can drive all the weights to smaller values. It becomes too costly for the cost to have large weights.This
leads to a smoother model in which the output changes more slowly as the input changes.

<img width="469" alt="error-L2-regularization" src="https://user-images.githubusercontent.com/63168221/103189914-cb6dc980-489c-11eb-99e3-bac9820599b5.png">

The cost function reduces dramatically after 2500 iterations. The test set accuracy increased to 93%.
Thus we are not overfitting the training data anymore and we plot the decision boundary as shown below.

<img width="478" alt="L2-regularization" src="https://user-images.githubusercontent.com/63168221/103190029-3f0fd680-489d-11eb-899c-0636f44a67ce.png">

**Step-3: Dropout**

Finally, dropout is a widely used regularization technique that is specific to deep learning. It randomly shuts down some neurons in each iteration.
When we shut some neurons down, we actually modify the model. The idea behind drop-out is that at each iteration, we train a different model that
uses only a subset of your neurons. With dropout,neurons thus become less sensitive to the activation of one other specific neuron, because that
other neuron might be shut down at any time.

<img width="478" alt="err-dropout" src="https://user-images.githubusercontent.com/63168221/103190379-ab3f0a00-489e-11eb-9ba1-3750647a2a5b.png">

The cost function reduces smoothly and reached a platuea after 5000 iterations. The test set accuracy increased to 95%.
Thus we are not overfitting the training data anymore and we plot the decision boundary as shown below.
<img width="471" alt="dropout" src="https://user-images.githubusercontent.com/63168221/103190448-0244df00-489f-11eb-9fba-5f1a423229a6.png">

**Step-4: Conclusions:**

| model | train acuracy | test accuracy |
| ---------| :-----------:|   ---------: |
| 3-layer NN without regularization | 95%  | 91.5% |
| 3-layer NN with L2-regularization  | 94%  | 93% |
|3-layer NN with dropout  | 93%  |  95% |
  
Dropout works great. The test accuracy has increased again (to 95%)! Our model is not overfitting the training set and does a great job on the test
set. Thus we used ML model to successfully predict the position of football in the field after the French goalkeeper kicks the football!
