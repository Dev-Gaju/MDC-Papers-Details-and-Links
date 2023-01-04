
### EfficineNet drawback:
- slow with large image dataset, for this batchsize make 1 like b7 used 560 and b0 used 224 image size.
- Depthwisw convolution used here which also slow
- If increase the size of image resolution atomatically increase width and height and not follow alpha, (beta)^2, (gama)^2 rules.
    
 ### EfficineNet V2 mitigate all the drawbacks.(Fused MBconv): 
 With progressive learning, our EfficientNetV2 significantly outperforms previous models on ImageNet and CIFAR/Cars/Flowers datasets
 
![image](https://user-images.githubusercontent.com/50872508/210134211-85e9304c-4cee-4e82-a356-c3a214a995f4.png)

 
 - Training aware architecture search(NAS), What we want better accuracy with less time and less parameter.
 - Progressive Learning - (Idea : progressibe growing of Gan and Mixmach papers)
 - Adjust Regularization whenever change image size(heavy Re Needed on Large Images)
 - Training have several stage and each stage they pick difference image size & Regularization.Training have four stage and each stage have 87 Nmber of epochs.In some stage the also mixup to image and increase accuracy.
 - Used Regulzrization and Data Augmentation : RandAugment, dropout, Mixup with Stcastic depth 0.8
 - In Large Network and Image size they do heavy regularization to prevent overfitting & better accuracy
 - 20% of training data used Neural architecture search(NAS). Which halp you find the best parameter like number of filter, height and width of filter, stride and stride with in each layers.
 - Lr schedular used for Optimization.
 Better Performance than VIT and also used less parameters(Vision Transformer Model).
 
