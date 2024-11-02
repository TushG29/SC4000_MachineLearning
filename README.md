# Welcome to our SC4000 Course Project
## About

This is a project for SC4000 (Machine Learning) where we worked on the Kaggle problem 'Recognizing Faces in the Wild'. 
Link: https://www.kaggle.com/c/recognizing-faces-in-the-wild. We have:

  1. Developed a Siamese architecture (Model 1) for comparing pairs of images that are represented in RGB and used transfer learning, custom fully connected layers and feature combination.The first layer of the model used InceptionResnetV1, pre-trained on the ‘vggface2’ dataset for obtaining the base encodings. The last five layers of the encoder were made trainable to allow the InceptionResnetV1 model to adapt to the requirements of kinship detection
  2. Designed Model 2 by enhancing non-correlation through three key modifications to Model 1: adjusted encoding layer by making 2 additional layers trainable, streamlined architecture of connected layers by reducing from four to two layers, and refined feature calculation by concatenating four selected features from the initial seven
  3. Implemented a SiameseNet wherein the image encoder used by it is a pre-trained Vision Transformer (ViT). The final layers of ViT were fine-tuned for kinship identification, with the majority of ViT parameters locked throughout training to preserve generic features and avoid overfitting. 
  4. Achieved a public score of 0.897 after performing weighted ensemble learning on the above three models

## Problem Definition
Can you determine if two individuals are related?

## Models Used
  1. Targeted Siamese Model. The irst layer of the model uses InceptionResnetV1, pre-trained on the ‘vggface2’ dataset for obtaining the base encodings. 
  2. Non-Correlated Siamese Model
  3. Vision Transformer

## Challenges
1. The images of people are not in a standardised format, thus the model may learn features which are irrelevant to the kinship recognition task. For example:  
   
   i) The images are shot at different locations, and shadows are present on the faces of the people due to poor and uneven lighting.  
   
   ii) There are numerous images of people wearing caps, and other objects close to their face which can mislead the model into finding non-kins similar.  
   
   iii) People of the same age, especially children, or the same gender, due to features like facial hair, may look similar despite being from different families.

2. The images provided in the sample have varying clarity, thus our solution must be flexible enough to detect facial features across a wide variety of photo qualities.

3. Moreover, training_relationships.csv only contains positive examples of people who are kins. Thus appropriate size and sample of negative pairs must be created.


## Conclusion
  1. The incorporation of negative sampling introduces a new dimension to the learning process, allowing the model to better differentiate between kinship and non-kinship relations. The use of Vision Transformers, a cutting-edge technology in image processing, further refines the model's ability to capture and analyse facial features crucial for kinship detection. 
  2. Finally, the exploration of model architectures and feature engineering techniques offers new insights to the kinship detection challenge. With ensemble learning, benefits of different architectures are combined to boost scores. We put efforts to experiment with novel ideas in addition to learning foundational computer vision concepts. The submission is convincing due to the relatively high performance achieved, and use of methods like Siamese architecture which can be intuitively understood.
