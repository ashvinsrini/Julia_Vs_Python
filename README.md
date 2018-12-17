# Julia_Vs_Python
First of all, I'd like to thank Prof. Vijay Kumar from MSRIT and Abhijith Chandraprabhu for having provided this opportunity to participate in Computational Machine Learning(CML) course organised at IISc under their tutelage as a part of CCE(Center for Continuing Education). Julia is truly an incredible language. The ease and speed of programming  in Julia is impressive!


This repo is for comparing time performances of Julia and Python on FASHION MNIST dataset.
This project was carried out in MacBookPRO 2014 edition with following hardware configurations. 
Processor: 2.5GHz, Intel Core i7
Meomry: 16GB 1600 MHz DDR3
Graphics: Intel Iris Pro 1536 MB 

FASHION MNIST data has a total of 60,000 training images with 10,000 test images with 10 different categories. 
Initially FFNN with same architectures is carried out in both Julia and Python. 


Python Architecture:
_________________________________________________________________
Layer (type)                 Output Shape              Param #   
=================================================================
dense_4 (Dense)              (None, 100)               78500     
_________________________________________________________________
dense_5 (Dense)              (None, 30)                3030      
_________________________________________________________________
dense_6 (Dense)              (None, 10)                310       
=================================================================
Total params: 81,840
Trainable params: 81,840
Non-trainable params: 0


Julia Architecture:
Any[Dense(784, 100, relu), Dense(100, 30, relu), Dense(30, 10, relu), softmax]


NOTE: Python architecture has extra trainable parameters because even biases are explicitly mentioned however, in Julia it is implicitly taken. 

It is found that Julia's compilation time is 133.9 seconds for 100 epochs with 61.2%
And for Python's compilation time is 237.6 seconds for another 100 epochs with 59.8% 

Now the second part of the project was to increase the accuracy. A CNN was considered instead of a FFNN. CNN has multiple convolutional/maxpooling/dropuouts layers as pre processing layers before feeding it into a dense NN. These preprocessing layers are designed primarily to extract image features. The primary increase in accuracy is because CNN makes use of preserved spatial structure as the entire 2 dimensional image is fed in rather than vectorizing them into a 1D array as done in FFNN. 

The accuracy was further increased to 86.75% 
