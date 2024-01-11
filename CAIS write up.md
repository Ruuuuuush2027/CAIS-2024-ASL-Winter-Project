#### name: Mo Jiang   USCid: 3924289422

1. In one or two sentences, present your project to us!
   
   My winter project intends to use a VGG 16 transfer learning model provided by Pytorch to classify 29 classes of American Sign Languages based on the images provided
2. Dataset: Indicate the dataset you chose to use, any preprocessing steps that were applied, as well as the reasoning behind these choices.
   
   The dataset I chose to use is the ASL Alphabet Dataset provided by Kaggle. There are a total of 87000 examples, and I applied resize, randomized crop, and normalization. The resize is used because of system constraints, and to train a model in a reasonable amount of time I must reduce the size of the input images. I used a randomized crop to create some randomness to avoid the model from overfitting, and normalization to make sure noises in images can have less effect on the model.
3. Model Development and Training: Discuss your model implementation choices, the training procedure, and the conditions you settled on (e.g., hyperparameters), and discuss why these are a good set for your task.
   
   To implement this model, I am not planning to train a new one from scratch, as it takes time and is often inefficient. Thus, I used a pretrained VGG 16 model adjusted the last few layers, and used this as my model. I used an Adam optimizer with a 0.001 learning rate and a linear_step_scheduler with a step_size of 50. I tried with a learning rate of 0.0001 but it hardly made any progress, thus 0.001 is the learning rate I chose. I set the epoch to be 10 as too less epochs will not yield good results, yet if the epoch is too high the model would take too much time to train, which is unrealistic with my current physical computing device.
4. Model Evaluation/Results: Present the metrics you chose and your model evaluation results. 
   
   Even though the training accuracy is over 80%, due to some strange reasons the testing accuracy is only around 1.36% - the model is severely overfitting. This could be due to my system error, or the overfitting occurring. For testing, I also used precision, recall, and F1 scores: the precision is 0.0523, the recall is 0.0136, and the F1 score is 0.0216.
5. Discussion: 
   1. How well do your dataset, model architecture, training procedures, and chosen metrics fit the task at hand? 
      
      In my opinion, my model architecture is suitable for this task. Because this task is essentially an image classification and a vgg 16 CNN architecture can extract useful information from images. Moreover, using transfer learning can also save time and cost, which is suitable for training a model with a large input dataset
   2. Can your efforts be extended to wider implications, or contribute to social good? Are there any limitations in your methods that should be considered before doing so?
      
      If the model can classify data more accurately (and does not overfit so much as it currently does), it could help recognize the sign languages. This could be incorporated into many technologies that assist the disabled who can only use sign language to communicate. One example is converting their signs into plain English so more citizens can understand what they are trying to convey, establishing a bridge of communication between people who cannot understand sign language and people who can. If the model classifies some characters wrongly, it could change the meanings of the original sentence in some scenarios. Due to this limitation, a model should not be applied unless it has a very high accuracy.  
   3. If you were to continue this project, what would be your next steps?
      
      If I have sufficient time and computing resources, I would try to use the full image instead of the resized ones when the machine is training, so the model can capture as many features as possible, improving accuracy. I would also give it higher training time, larger architectures, and more techniques to avoid overfitting. But for now, the main task is to discover where the problem is and why the overfitting is so extreme (80% training accuracy vs. 1.3% testing accuracy)
      
      