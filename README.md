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

# data/
# ├── train/
# │   ├── face_train/
# │   │   ├── image1.jpg
# │   │   ├── image2.jpg
# │   │   └── ...
# │   ├── eyes_train/
# │   │   ├── image1.jpg
# │   │   ├── image2.jpg
# │   │   └── ...
# │   └── mouth_train/
# │       ├── image1.jpg
# │       ├── image2.jpg
# │       └── ...
# └── test/
#     ├── face_test/
#     │   ├── image1.jpg
#     │   ├── image2.jpg
#     │   └── ...
#     ├── eyes_test/
#     │   ├── image1.jpg
#     │   ├── image2.jpg
#     │   └── ...
#     └── mouth_test/
#         ├── image1.jpg
#         ├── image2.jpg
#         └── ...

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

