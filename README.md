## Research article : https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=10210543

# Dataset 
download : https://drive.google.com/drive/folders/1zyjYSncGBTl7WWFKGuqhXRckrqS-DBu-?usp=drive_link

after download dataset, create `data` folder and place the dataset into the directory

The dataset contain 2.865 image that separated into 3 subset class  `face`, `eyes`, `mouth ` and for each class we have another 7 different class according to the human facial expression
* angry
* fear
* happy
* neutral
* sad
* surprise
* disgust

We resize each subset class according to the journal:
* `face` 38 x 38
* `eyes` 30 x 62
* `mouth` 30 x 38

we use ratio `8:2` for the train data and test data

The structure of the dataset

<img width="174" alt="test" src="https://github.com/ESPB0808/HFT-CNN/assets/115124715/ea8f250b-a6d4-4d9c-b5f0-8ebeef9b39e4">
<img width="174" alt="train" src="https://github.com/ESPB0808/HFT-CNN/assets/115124715/348641b9-320e-456c-bab0-49f453e099b3">


## Requirements
* Tensorflow 
* OpenCV
* Matplotlib 

# Instalation
## Clone repository
```
git clone https://github.com/ESPB0808/HFT-CNN.git
```
Make virtual environment in anaconda
```
conda create -n [your env name] python=3.9 jupyterlab
```
activate the environment
```
conda activate [your env name]
```
and then install the following package
```
pip install tensorflow
```
```
pip install opencv-python
```
```
pip install matplotlib
```

or you can install the `requirements.txt`, make sure that you already in the clone directory
```
pip install -r requirements.txt
```
# Research Results Report
## Background of this Research
The background of this research involves specific characteristics in facial expression recognition, where changes in expression (primarily) are caused by changes in facial features and muscles. The research findings indicate that the eyes and mouth play crucial roles in facial expression recognition. However, it's noted that most traditional convolutional networks focus solely on global facial features, disregarding the features of the eyes and mouth. Therefore, the author proposes a solution in the form of a three-channel convolutional neural network framework for facial expression recognition, which combines various levels of features. This HFT-CNN architecture aims to address these limitations and enhance the accuracy of facial expression recognition by considering the significant roles of the eyes, mouth, and global facial features.

## Literature Review
The HFT-CNN architecture employs 3 different CNN sub-models to handle three main parts of the face: the overall face, eyes and eyebrows, and the mouth. The results from these three models are then feature-extracted and merged into a main model. Each image is fed into its respective CNN channel for training purposes.

![feature_fusion_model](https://github.com/ESPB0808/Facial-Expression-Recognition-Using-Hierarchical-Features-With-Three-Channel-CNN/assets/30742772/ddb4cf1b-70e1-4165-b16b-75b72ed51a7e)

## Research Workflow

![untitled](https://github.com/ESPB0808/Facial-Expression-Recognition-Using-Hierarchical-Features-With-Three-Channel-CNN/assets/30742772/3b09f975-9960-4565-a861-45436bd4db40)

## Dataset
To implement HFT-CNN, we created our own dataset consisting of 2,865 images categorized into 7 labels with an 8:2 ratio. Below is the structure of the utilized dataset:

![Screenshot 2024-01-10 at 07 41 30](https://github.com/ESPB0808/Facial-Expression-Recognition-Using-Hierarchical-Features-With-Three-Channel-CNN/assets/30742772/6554d30e-b429-43af-b7c7-9ebf11f1133f)

Example Dataset: 
| Eye      | Face    | Mouth   |
| -------- | ------- | ------- |
| ![Screenshot 2024-01-10 at 07 44 34](https://github.com/ESPB0808/Facial-Expression-Recognition-Using-Hierarchical-Features-With-Three-Channel-CNN/assets/30742772/e1d95a5d-67fd-473d-9030-6628a28638a6)  | ![Screenshot 2024-01-10 at 07 46 27](https://github.com/ESPB0808/Facial-Expression-Recognition-Using-Hierarchical-Features-With-Three-Channel-CNN/assets/30742772/fe9e6ab0-6a43-43fe-807e-858c333ff073)    |  ![Screenshot 2024-01-10 at 07 46 51](https://github.com/ESPB0808/Facial-Expression-Recognition-Using-Hierarchical-Features-With-Three-Channel-CNN/assets/30742772/27da7490-0594-4fb3-a3de-3a83510c140c)   |

## Program Implementation Flow

![Screenshot 2024-01-10 at 07 48 26](https://github.com/ESPB0808/Facial-Expression-Recognition-Using-Hierarchical-Features-With-Three-Channel-CNN/assets/30742772/5c1343da-0ed9-487d-88cb-1acc25036932)

## Research Scheme
The research scheme conducted involves comparing two CNN models using the same dataset. The purpose behind this comparison is to substantiate the claims made by the HFT-CNN research. As the HFT-CNN comprises sub-models (face, eyes and eyebrows, mouth), a comparison will be made with Kusuwa's CNN model, where the same model will be used to train different datasets. Here is a clearer depiction of Kusuwa's CNN model for better understanding.

![cnn_kusuwa](https://github.com/ESPB0808/Facial-Expression-Recognition-Using-Hierarchical-Features-With-Three-Channel-CNN/assets/30742772/fa92b11c-a1ad-4eaa-bb5a-5f2e01a4b5de)

The testing stages used to validate the HFT-CNN claims include:

* Comparing the accuracy and training speed of HFT-CNN sub-models with Kusuwa's CNN model.
* Contrasting the accuracy and training speed of the combined HFT-CNN model with the accuracy and training speed of each Kusuwa CNN model.

As the Kusuwa CNN model lacks integration among the face, eyes and eyebrows, mouth models, the author devised a formula to calculate the overall accuracy, which will be obtained as follows:

![Screenshot 2024-01-10 at 07 53 09](https://github.com/ESPB0808/Facial-Expression-Recognition-Using-Hierarchical-Features-With-Three-Channel-CNN/assets/30742772/fb83b03d-a2ae-437e-93fd-8b3d88407055)

## Results
* Accuracy Comparison:

| Channel           | CNN Kusuwa | HFT-CNN |
| :---------------- | :--------: | :-----: |
| Face              |    0.984   |  0.616  |
| Eyes & Eyebrows   |    0.998   |  0.551  |
| Mouth             |    0.964   |  0.385  |
| Combine           |    0.984   |  0.955  |

* Training Speed Comparison

| Channel           |   CNN Kusuwa  |   HFT-CNN  |
| :---------------- | :-----------: | :--------: |
| Face              |    1m 54.9s   |  1m 42.7s  |
| Eyes & Eyebrows   |    1m 52.8s   |  1m 6.8s   |
| Mouth             |    1m 18.6s   |  1m 36.2s  |
| Combine           |       -       |  9m 32s    |

Both models were trained with 100 epochs.

## Conclusion

The conclusion drawn from the implementation experiment of HFT-CNN, where the author aimed to validate the claim that HFT-CNN exhibits higher accuracy levels compared to traditional CNN models, is inconclusive. However, this could change due to several factors that might influence these results, such as dataset quality, hardware performance, and tuning of CNN model hyperparameters.
