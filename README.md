# FederatedLearningDatasets

1. FEMNIST

  * **Overview:** Image Dataset
  * **Details:** 62 different classes (10 digits, 26 lowercase, 26 uppercase), images are 28 by 28 pixels (with option to make them all 128 by 128 pixels), 3500 users
  * **Task:** Image Classification

2. Sentiment140

  * **Overview:** Text Dataset of Tweets
  * **Details** 660120 users
  * **Task:** Sentiment Analysis

3. Shakespeare

  * **Overview:** Text Dataset of Shakespeare Dialogues
  * **Details:** 1129 users (reduced to 660 with our choice of sequence length. See [bug](https://github.com/TalwalkarLab/leaf/issues/19).)
  * **Task:** Next-Character Prediction

4. Celeba

  * **Overview:** Image Dataset based on the [Large-scale CelebFaces Attributes Dataset](http://mmlab.ie.cuhk.edu.hk/projects/CelebA.html)
  * **Details:** 9343 users (we exclude celebrities with less than 5 images)
  * **Task:** Image Classification (Smiling vs. Not smiling)

5. Synthetic Dataset

  * **Overview:** We propose a process to generate synthetic, challenging federated datasets. The high-level goal is to create devices whose true models are device-dependant. To see a description of the whole generative process, please refer to the paper
  * **Details:** The user can customize the number of devices, the number of classes and the number of dimensions, among others
  * **Task:** Classification

6. Reddit

  * **Overview:** We preprocess the Reddit data released by [pushshift.io](https://files.pushshift.io/reddit/) corresponding to December 2017.
  * **Details:** 1,660,820 users with a total of 56,587,343 comments. 
  * **Task:** Next-word Prediction.

7. CIFAR 10 / CIFAR 100

- CIFAR10 and CIFAR100 are image classification datasets with 60,000 32 × 32px color images distributed evenly over 10 and 100 classes respectively (50,000/10,000 train/test split). They are benchmark computer vision datasets, and although they lack a natural noni.i.d. partitioning, we artificially create one by giving each client images from only a single class.  (from FetchSGD)