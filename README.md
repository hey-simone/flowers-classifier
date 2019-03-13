# flowers-classifier
A Flower Classifier with Keras and Tensorflow
In this notebook, we have a look at classifying flowers with **convolutional neural networks** in **Keras** using the **TensorFlow** backend.

### Dataset
The dataset used can be found on Kaggle here: https://www.kaggle.com/alxmamaev/flowers-recognition. It contains 4242 images of 5 different categories of flowers which were scraped from various sources on the web. The categories are **daisy, dandelion, rose, sunflower, and tulip**. These photos need to be preprocessed as they are of varying dimensions and will not fit into the convnet as is. Some of the unprocessed images from each category are shown below.

![Sample Images](https://storage.googleapis.com/cp100-53456789/Image-Samples.png)

I chose this dataset because though it is small it has similar features to some of the training classes of ImageNet. This means that they can be used to do **transfer learning** and **fine-tuning** effectively with pre-trained models from `keras.applications`. The ImageNet dataset actually has more photos for the plant category than the category for the cats and dogs. This is significant because a precedent I am using on cats and dogs from Francois Chollet's *Deep Learning with Python* performed very well (97% accuracy with the validation set) using fine-tuning with a **VGG16** pre-trained model. Thus it seemed like a sensible starting point.


Thus, we follow a similar approach here which is detailed further in the rest of the notebook. This dataset is slightly more challenging than ImageNet itself as the photos are taken in more natural contexts in a similar way to the precedent mentioned. Thus it is expected to perform similarly to the precedent with fine-tuning (Null Hypothesis).

### Overview
We look at preparing, importing and exploring the data with some light preprocessing. Then visualize the data in the notebook with a helper function after preprocessing. 

Next, we move on to some more preprocessing with normalization and data augmentation and the models. This section accounts for the bulk of the notebook. We create a baseline model with a basic convnet to compare the performance of the other models. This model overfits, so we add data augmentation and dropout. Then we use VGG16 and DenseNet161 in various configurations for feature extraction and fine-tuning. Then we evaluate the best model on the test set to verify performance.

Finally, we have the conclusion, possible directions for future work and references.

### Outcomes
***The best model was a fine-tuned DenseNet161 model with 91% test set accuracy and 90% validation set accuracy.*** Thus the null was rejected as the dataset performed worse than the precedent. This is likely because the classification task here is more granular than the precedential task on the generic classes of cats and dogs so the problem of classifying specific flowers is a bit more challenging.

**See the notebook for more.**
Saved models created during training can be found [here](https://drive.google.com/file/d/1UY5JQhPeFcemuT432hOxxJVm6CBrPuwi/view?usp=sharing) (~2MB) .
