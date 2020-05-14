# Finger Digit Classification

* **Problem:** Attempt to identify how many fingers are raised in an image.

## Phase 1: Gathering Data

### Training Images:
![](./screenshots/sampleTrainImg.png)

### Test Images:
![](./screenshots/sampleTestImg.png)

### Data Distribution and Base Accuracy:
![](./screenshots/distGraph.png)

## Phase 2: Build Overfitting Models
Attempt to build a model that overfits on the training set.

### Many Layer Model
Build a model with many layers and train it to score 100% on the training data.
![](./screenshots/ManyLayered.png)

### Output as Input Model
Build a model where training data includes the true output in the final channel.
![](./screenshots/OutAsIn.png)

### Results: Which model learned faster.
![](./screenshots/overfitGraph.png)

From the graph, it might seem that the Many Layer model overfit faster but the many layer model was trained with ImageGenerators and was exposed to more images for each epoch, which is why it converged earlier then the Output as Input model. In reality the Output as Input model actually finished training at a much master time than the Many Layer model.

## Phase 3: Split and Evaluate
Start training, and find the a good architecture:
* How to build an architecture:
    I started off with a basic architecture, layers are gradually added, once I start to notice that the accuracy start to decrease, I start working on the models with the best accuracy so far and start fine tuning it.

![](./screenshots/bestModel.png)
![](./screenshots/bestModelLCurve.png)

## Phase 4: Effects Of Augmentation
Find the optimal augmentation for the input data to ensure that the model gets the most out of learning. The result shows that augmentation is best around 10-20%, and too much augmentation will completely invalidate the data.

With the best model from Phase 3, train on different augmentation intensities:
![](./screenshots/bestAugGraph.png)
