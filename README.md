# FederatedLearningDatasets

1. FEMNIST

  * **Overview:** Image Dataset
  * **Details:** 62 different classes (10 digits, 26 lowercase, 26 uppercase), images are 28 by 28 pixels (with option to make them all 128 by 128 pixels), 3500 users
  * **Task:** Image Classification
  * Federated EMNIST is an image classification dataset with 62 classes (upper- and lower-case letters, plus digits) (Caldas et al., 2018), which is formed by partitioning the EMNIST dataset (Cohen et al., 2017) such that each client in FEMNIST contains characters written by a single person. （from FetchSGD）




2. Sentiment140

  * **Overview:** Text Dataset of Tweets

  * **Details** 660120 users

  * **Task:** Sentiment Analysis

  * **数据格式**

      * 训练集

          * ```json
            {
                "users": ["michelleemilie", "Norri"],
                "num_samples": [2, 2],
                "user_data": {
                    "michelleemilie": {
                        "x": [["1983468420", "Sun May 31 13:12:51 PDT 2009", "NO_QUERY", "michelleemilie", "Headache, but I'll fix that soon. Leaving in about an hour ", "training"], 
                            ["2181302206", "Mon Jun 15 11:38:37 PDT 2009", "NO_QUERY", "michelleemilie", "http://twitpic.com/7hcjq - Ice Age 3! I cant wait to see that movie ", "training"]],
                        "y": [1, 1]},
                    "Norri": {
                        "x": [["1960390654", "Fri May 29 07:53:22 PDT 2009", "NO_QUERY", "Norri", "Just learned the first 30 seconds of Satriani's &quot;Ten Words&quot; by ear. Took me over an hour. I sure hope this gets easier as I go along ", "training"], 
                            ["1990316264", "Mon Jun 01 04:31:44 PDT 2009", "NO_QUERY", "Norri", "Fingers are freezing, time for my hobo gloves ", "training"]], 
                        "y": [1, 1]}
                }  
            }
            ```

    * 测试集

      * ```json
        {
            "users": ["michelleemilie", "Norri"],
            "num_samples": [1, 1],
            "user_data": {
                "michelleemilie": {
                    "x": [["2056916213", "Sat Jun 06 12:02:02 PDT 2009", "NO_QUERY", "michelleemilie", "I've got a damn headache  wtf.", "training"]],
                    "y": [0]},
                "Norri": {
                    "x": [["1960397056", "Fri May 29 07:53:59 PDT 2009", "NO_QUERY", "Norri", "@robzonenet Always a pleasure ", "training"]],
                    "y": [1]}
            }  
        }
        ```

        



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

8. FedVision - Street Dataset

* **Overview:**  
A real-world object detection dataset that annotates images captured by a set of street cameras based on object present in them, including 7 object categories. In this dataset, each or every few cameras serve as a device. Thec federated street dataset captures common objects on the streets by CCTV cameras, including motobikes, buckets, umbrella, and so on.

* **Details:** 

|  Dataset |  number of devices | Total samples | number of categories|
|  ----  | ----  |  ----  | ----  |
| Street | 5,20| 956| 7|

* **Task:**  Object detection

* **Details:** *Street_Dataset.tar* contains the image data and ground truth for the train and test set of the street data set.

  * Images: The directory which contains the train and test image data.
  * trainlabel.json: The annotations file is saved in json format. trainlabel.json is a list, which contains the annotation information of the Images set. The length of list is the same as the number of image and each value in the list represents one image_info. Each image_info is in format of dictionary with keys and values. The keys of image_info are image_id, device1_id, device2_id and items. We split the street data set in two ways. For the first, we split the data into 5 parts according to the geographic information. Besides, we turn 5 into 20. Therefore we have device1_id and device2_id. It means that we have 5 or 20 devices. items is a list, which may contain multiple objects.

* **Evaluation:**
We use the standard PASCAL VOC 2010 mean Average Precision (mAP) for evaluation (mean is taken over per-class APs).
To be considered as a correct detection, the overlap ratio  between the predicted bounding box $B_p$  and ground truth bounding box $B_{gt}$ must exceed 0.5 (50%) by the formula below。
$$
    a_o = \frac{area(B_p\bigcap B_{gt})}{area(B_p\bigcup B_{gt})}
$$
The computation of the average precision (AP) measure has been changed in VOC2010 to improve precision and the ability to measure differences between methods with low AP. It is computed as follows:
  * 1. Compute a version of the measured precision/recall curve with precision monotonically decreasing, by setting the precision for recall r to the maximum precision obtained for any recall $r' \ge r$.
  * 2. Compute the AP as the area under this curve by numerical integration. No approximation is involved since the curve is piecewise constant. For  classes, mAP is the average of APs.

$$
  mAP = \frac{\Sigma_{i = 1}^kAP_i}{k}
$$

9. EMNIST

`EMNIST`全名`Extended MNIST`，这是一个包含英文字母+数字的数据集

**EMNIST分类方式**

EMNIST 主要分为以下 6 类：

- By_Class ： 共 814255 张，62 类，训练集 697932 张，测试集 116323 张
- By_Merge： 共 814255 张，47 类，训练集 697932 张，测试集 116323 张
- Balanced : 共 131600 张，47 类，训练集 112800 张，测试集 18800 张
- Digits ：共 28000 张，10 类，训练集 240000 张，测试集 40000 张
- Letters : 共 103600 张，37 类，训练集 88800 张，测试集 14800 张
- MNIST ： 共 70000 张，10 类，训练集 60000 张，测试集 10000 张

**SCAFFOLD**

  * Karimireddy divides [EMNIST](https://arxiv.org/abs/1702.05373v1) among N = 100 clients as follows: for s% similar data we allocate to each client s% i.i.d. data and the remaining (100-s)% by sorting according to label(cf. Hsu et al. (2019)). (from SCAFFOLD) 
  * 在这个工作中作者认为给客户端分配数据时，如果more shuffled，意味着客户端之间数据分布越相似。0% similarity意味着按标签排序后再进行分配，此时数据异质性很高。100% similarity意味着完全随机地打乱数据，此时数据时独立同分布的（即每个客户端中含有的标签都差不多）
  * 不过文章中没有具体讲用的是哪种类型的EMNIST
  * EMNIST数据集：[下载地址](https://www.westernsydney.edu.au/bens/home/reproducible_research/emnist)




10. MovieLens
* Overview: 结构化数据
* URL:
  * 官网：https://grouplens.org/datasets/movielens/
  * MovieLens Latest:http://files.grouplens.org/datasets/movielens/ml-latest.zip
  * MovieLens 25M:http://files.grouplens.org/datasets/movielens/ml-25m.zip
  * MovieLens 1M:http://files.grouplens.org/datasets/movielens/ml-1m.zip
* Details:数据集包含了用户对某些视频的评分和视频相关的一些标签属性，其中评分分为5个等级。MovieLens 25M里面还有用户对视频的文本评价，MovieLens 1M里面包含用户的相关信息。
* Task：推荐系统
* 数据容量：MovieLens 1M包含1000209个匿名用户对3900个视频的评分
* 适用联邦学习场景：由于用户信息、视频信息和评分表都是天然分开的，适用于纵向联邦
* 数据格式：
  * ratings.dat:UserID|MovieID|Rating|Timestamp
  * users.dat:UserID|Gender|Age|Occupation|Zip-code
  * movies.dat:MovieID|Title|Genres



11. Credit
* Overview: 结构化数据
* URL:
  * Credit 1：https://www.kaggle.com/c/GiveMeSomeCredit/data
  * Credit 2： https://www.kaggle.com/uciml/default-of-credit-card-clients-dataset
* 相关论文：SecureBoost: A Lossless Federated Learning Framework
* Details：这两个数据集包含用户的一些属性，例如性别、受教育程度等，Credit 1包含150000个样本10个属性，Credit 2包含30000个样本25个属性，学习目标是预测用户是否会还款违约
* Task：分类
* 适用联邦学习场景：可用于纵向联邦（在论文SecureBoost，作者将该数据集手动竖直切分，应用到纵向联邦学习）
