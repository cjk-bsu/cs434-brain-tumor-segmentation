# Applying U-Net for Medical Image Segmentation: A Case Study

## By: Carson Keller

## Introduction
This project serves as a case study in utilizing a neural network for image segmentation on a dataset of MRI image files to assess its accuracy in differentiating brain tumor mass from healthy tissue. Further, this project attempts to affirm this process as a proof of concept, prior to wider adoption in real-world applications. Additionally, it also aims to evaluate the performance of different combinations and variations of deep learning model architectures, metrics, and loss functions informed by academic literature. This is done in the hope of finding a most successful, most performant composite model structure that yields the best results. This work is so important when the tangible impacts of better AI models with higher accuracy are better surgeries, more accurate tumor excision margins, and lower mortality rates. As the use of AI becomes more prevalent in medicine, the ramifications of these improvements can quite literally be life or death. 

## Source Code & Dataset
This project was completed in an `.ipynb` [notebook file](./src/brain-tumor-segmentation.ipynb) on the Google Colab platform. All necessary packages are specified and imported in the first block of the notebook, and all are needed for the code to successfully execute. Further, mutual compatibility between packages is necessary. As packages update from publishing, users will have to verify version intercompatibility as version updates may occur.

Additionally, the dataset utilized in this experiment is required. While it was included in the `.zip` file submission of the project iself, it is too large to be uploaded to GitHub. However, the dataset is publicly available for download [here](https://www.kaggle.com/datasets/awsaf49/brats20-dataset-training-validation) on Kaggle. Without any alteration to the source code, the notebook cannot simply be run on any machine out of the gate. Users will have to correct the primary `PATH` variable to their current directory as well as source and download the dataset themselves and ensure appropriate directory structure. 

## Operation Suggestions

Due to the extreme memory and computational demands of training the model on this dataset, it is recommended to utilize GPU hardware acceleration to expedite training and processing should a user decide to run this code. The initial training was performed using Google's online Colab utility, but other platforms may be utilized or local GPU resources may suffice. Utilizing a GPU can mean the difference between training epochs that take <4 mins or >5 hours. Proceed with caution.

## Results

Utilizing the U-Net neural network architecture was highly successful in segmenting MRI brain scan images. After training, the resultant model was able to isolate tumor tissue from normal brain tissue with a test accuracy of 99.42% and a test loss of 1.78%. 

![Training Statistics](/paper_resources/training%20statistics.png)

Numerically, these results seem quite impressive. In context, however, the 0.58% error remaining is quite meaningful. Referencing the sample result image below, the error in pixel-to-pixel classification can be seen in the accuracy at the tumor margins. While tumor segmentation is generally correct, there are some minor instances where pixel classification creeps into healthy tissue just slightly or doesn't quite include all of the tumor tissue. In real-world applications, this could result in incomplete tumor excision or unnecessary removal of healthy tissue.

![Example Output](/paper_resources/example%20result.png)

That being said, the results are still quite impressive for a baseline proof of concept and definitely evidence enough to warrant further exploration and development of more accurate, capable models to approach this and similar tasks. Full, detailed results of the project can be found in the written paper [here](/paper.pdf).

## Copyright & License

See License Agreement [here](/LICENSE).