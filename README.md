## Skin Cancer Detection

#### Summary
Deep Learning is helping many industries across the world helping lots of people. One of the biggest impact is happening in health sector. We tried the latest CNN model's to detect **benign** and **malignant** mole which might turn out to be cancerous to the patient. First we wanted to detect the cancer on 7 types mole with 10015 images.

- Actinic Keratoses
- Basal cell carcinoma
- Benign keratosis
- Dermatofibroma
- Melanocytic
- Melanoma
- Vascular

The dataset: [HAM10000](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6091241/)


#### Data
There was a huge class imbalance in the dataset so we used tensorflow's image_generator dataset to create new images to have more balance in the data. Also, we are planning to create GAN model to create new images to get rid of the class imbalance


#### Model
We used ResNet50 to classify 7 types of moles with pre-trained weights which is provided by Keras.
**The Architecture**
- 1 Normal Conv2d
- 1 Conv Block
- 2 Identity
- 1 Conv Block
- 3 Conv Block
- 1 Conv Block
- 5 Identity
- 1 Conv
- 2 Identity
- 1 Average Pool
- Flatten to Fully Connected layer

#### Results

| Attempt | #Accuracy | #Precision | #Recall | #Notes |
| :---: | :---: | :---: | :---: |
| First | %76 | %70 | %72 | Baseline model|
| Second | %80 | %72 | %73 | ResNet50 |
| Second | %81 | %72 | %73 | ResNet50 + Image Generator |

#### Conclusions

The class imbalance issue was at hand and also it would be better to classify images as a binary classification task as **benign** or **malignant** . Which than let the doctors do their job. It is important at this task to not have Type I error where positive it malignant mole.
