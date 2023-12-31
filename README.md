# Traffic-Sign-Classification

## Description of Project

1. Goal:
The objective of this project is to test and compare different CNN model architectures’ robustness in identifying different types of Graffitied traffic signs.

2. Motivation:
Within the skyrocketing industry of self-driving smart car, safety has always been an essential concern that all car manufacturer and innovator need to address while updating vehicle’s other attributes such as speed and energy consumption.  In this topic, abiding to the traffic signs is a significant component. However, in real life, some of the traffic signs are often damaged or doodled; therefore, it’s vital for all self-driving vehicles to be able to identify traffic signs robustly and consistently.

3. Benefit:
In real life situations, some traffic signs that we see on the streets are not in perfect conditions: they are sometimes damaged or scribbled on. In this case, finding the most accurate model is just as vital as finding the most robust one.

## Description of Repository

1. Dataset Link: https://drive.google.com/file/d/1ZAjCtX0_zZ-qmmMSxxeCfIvp8IXD5ibd/view?usp=sharing
2. Modified Dataset Link: https://drive.google.com/file/d/19tspbi0lvCZHIUcfXe6hC_giNp10wHjJ/view?usp=sharing
3. image_change.ipynb: The code to modify the dataset
4. labels.csv: label classes
5. Traffic_Sign_Classification(2).ipynb: The main file where we analyzed the dataset
6. Traffic Signs Classification.pdf: PowerPoint

## Code Structure

* Part 1: import Traffic Sign Dataset from Kaggle
* Part 2: Data Augumentation and Rescaling
* Part 3: Build LeNet5, ResNet50, VGG16, and InceptionV3 models, compile and fit to get accuracy and validation accuracy
* Part 4: Randomly change the color of certain pixels in each image to imitate the real-life traffic signs that are usually damaged or distorted in certain ways
* Part 5: Use previously trained models to evaluate the modified dataset to see the robustness of the models
* Part 6: Run Transfer Learning on all 4 models (Two options: Freeze 50%, Freeze 100%) 

## Example Commands of Code Execution

* Example of LeNet5 model construction
![image](https://user-images.githubusercontent.com/102041218/208345623-90719719-9049-4889-950a-fe3c40f0daf7.png)

* Example of LeNet5 Transfer Learning
![image](https://user-images.githubusercontent.com/102041218/208331433-47df0207-72aa-441f-9d51-3c73ad0cf2dd.png)

## Original Dataset Sample


![002_1_0017](https://user-images.githubusercontent.com/102041218/208332210-f4b9fe3b-56da-4f6e-b9f9-0087cf6dabbe.png)
![007_1_0001](https://user-images.githubusercontent.com/102041218/208332354-45927086-4ab1-48e6-9f37-50979c9f0627.png)

## Modified Dataset Sample

![006_0003](https://user-images.githubusercontent.com/102041218/208332790-746e3888-82eb-4bd2-a14f-3aa723e9e7a5.png)
![022_1_0001](https://user-images.githubusercontent.com/102041218/208332837-15ab072d-309a-48c9-b39d-b4c5a8e66471.png)

## Results (including charts/tables)

1. Accuracy on original traffic sign dataset
<img width="824" alt="截屏2022-12-18 下午10 39 06" src="https://user-images.githubusercontent.com/85027205/208342797-e21f12a0-6244-4b9b-9c89-74d44f45bef9.png">

2. Validation Accuracy on modified traffic sign dataset 
<img width="771" alt="截屏2022-12-18 下午10 36 11" src="https://user-images.githubusercontent.com/85027205/208342928-c0008ba6-cd93-4517-bb85-cf60c7d887ee.png">

3. Change of Validation Accuracy between original data and modified data
<img width="486" alt="截屏2022-12-18 下午10 47 12" src="https://user-images.githubusercontent.com/85027205/208343563-2d1138b7-4b37-46ae-8383-d182589fa6b1.png">

4. Transfer Learning Accuracy
* Train Accuracy:

<img width="798" alt="截屏2022-12-18 下午10 50 40" src="https://user-images.githubusercontent.com/85027205/208343952-0d95a697-a1bb-469d-8138-0c25301d3bf2.png">

* Validation Accuracy:

<img width="798" alt="截屏2022-12-18 下午10 51 15" src="https://user-images.githubusercontent.com/85027205/208343993-d14e6eaf-07d9-424b-bd29-7f552b33273b.png">

## Observations

1.  Accuracy:
* InceptionV3 > VGG16 > LeNet5 > ResNet50
* Compare LeNet-5, ResNet-50, VGG-16, and InceptionV3’s model accuracy in classifying various traffic signs on the traffic Sign Dataset to select the best model.

2. Robustness Against Graffitied Traffic Signs:
* InceptionV3 > VGG16 > LeNet5 > ResNet50 
* The validation accuracy of the models decreased when tested on the modified validation set compared to the original validation set. This decrease in accuracy indicates that the models are less effective at classifying the modified traffic signs than the original traffic signs. But it is worth noting that the decrease in validation accuracy was relatively large for VGG-16 and Inception-V3, which still achieved relatively high accuracy on the modified validation set. This suggests that these two models may be more robust to changes in the training data than the other models.

3. Transferability:
* (LeNet5 and Inception-V3) ↑ 
* (ResNet50 and VGG-16) ↓
* When using transfer learning to fine-tune the models on the modified training set, the validation accuracy increased for some models (LeNet5 and Inception-V3) and decreased for others (ResNet50 and VGG-16). Overall, these results suggest that the effectiveness of transfer learning can vary depending on the specific model and the task at hand. In this case, transfer learning was able to improve the performance of some models on the modified validation set, but had a negative effect on the performance of others. It's important to carefully consider the capabilities and limitations of different models when choosing a model for a specific task and to carefully evaluate their performance on the relevant data.
