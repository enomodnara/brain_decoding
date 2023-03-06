# semantic-brain-decoding

This repository contains the code to support the "Semantic Brain Decoding" paper.

![Pipeline](https://user-images.githubusercontent.com/127113003/223122943-e42de9e2-38f3-4569-a988-7ff005d80393.png)

In this work, the idea is that the brain process images extracting relevant information in form of features which are similar to the ones extracted by the latent space (last layer before classification) of a CNN. Those "Semantic" features lives in a space (fMRI measurements) that could be homeomorphic to the latent space of the CNN.
We exploited a linear model to estimate the features from brain activity and a kNN to mimic a bottom-up and top-down perception process in the visual cortex and use the classification labels to condition a latent diffusion model to generate images with similar concepts and contents to the target ones used as stimuli during the fMRI experiment, starting from this neurophysiological data.

To reproduce the results, you will need to:

1) Download the processed original fMRI dataset from https://figshare.com/articles/dataset/Generic_Object_Decoding/7387130 and put the downloaded fMRI files in the "data/fMRI/GOD" folder 
2) Download the image stimuli used in the fMRI experiment compiling the form https://forms.gle/ujvA34948Xg49jdn9. After download, training and test images should go under the "data/fMRI/imagenet/images" folder, respectively in the training and test subfolders. In the parent (images) folder place the .csv files.
3) Download the ImageNet latent space features from https://drive.google.com/drive/folders/1wHN1QZkwjan1jp6wDrezWNcCm8kVqOeJ?usp=share_link    
3) Train the models using the train_models.ipynb notebook or download our pretrained models from https://drive.google.com/drive/folders/1UX84IB-l1I_mvhxeDiLgVeVfs1SrjuzX?usp=share_link.

5) Finally, use the semantic_brain_decoding.ipynb notebook to predict labels from brain activity and generate semantic reconstructions.


Below, you can see the comparison between our reconstructions and related work over the same dataset.

![Comparison](https://user-images.githubusercontent.com/127113003/223122902-13fb57a1-34bb-4df4-86b2-12cf572cb1df.png)


To add some quantitative measurements to our work, we measured the Wu-Palmer distance over predicted and real classes to measure semantic similarity


![Grafo](https://user-images.githubusercontent.com/127113003/223122932-afe01c55-3605-477d-88bf-509047751ee1.png)

![WuPalmer](https://user-images.githubusercontent.com/127113003/223122947-f8f4f8b9-6a38-45a8-b90c-eba620a69d88.png)




