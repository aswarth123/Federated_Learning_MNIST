# A Federated Learning approach based on SVM
## Support Vector Machines
Support Vector Machines (SVM) is a supervised machine learning algorithm used to analyze data for classification. The algorithm calculates one or more hyperplanes which separates the data points of one class from the other one. The hyperplane which has the largest margin between the two classes is selected. A hyperplane can be represented as the set of points x satisfying 1 where w is the normal vector to the hyperplane and b is the offset of the hyperplane from the origin. The input x belongs to:-
- class -1 if ![equation](https://latex.codecogs.com/png.latex?%5Cinline%20%5Cbg_white%20w%5E%7BT%7Dx%20&plus;%20b%20%3C%20-1)
- class +1 if ![equation](https://latex.codecogs.com/png.latex?%5Cinline%20%5Cbg_white%20w%5E%7BT%7Dx%20&plus;%20b%20%3E%201)
  
In cases of non-linear problem , SVM is extended with the hinge loss function and the problem becomes an optimization problem to reduce this loss. 
- ![equation](https://latex.codecogs.com/png.latex?%5Cinline%20%5Cbg_white%20max%280%2C%20%281%20-%20y_%7Bi%7D.%28w%5E%7BT%7Dx%20&plus;%20b%29%29%29)
## Federated SVM
Federated SVM makes use of hinge loss function and updates the model parameter w as ![equation](https://latex.codecogs.com/png.latex?%5Cinline%20%5Cbg_white%20%5Comega%20%5Crightarrow%20%5Comega%20-%20%5Ceta/B%5Csum_%7Bi%5Cepsilon%20B_%7Bk%7B%5Ccolor%7BPink%7D%20%7B%5Ccolor%7BPink%7D%20%7D%7D%7D%20%7D%20y_%7Bi%7D.x_%7Bi%7D) . The below picture gives an overview of federated SVM :-
<p align="center" width="100%">
    <img width="700" height="350" src="https://i.postimg.cc/tgpMdTsK/fedSVM.png"> 
</p>

## Federated SVM for classifying MNIST dataset
The dataset used here for validating the federated SVM is MNIST handwritten digits dataset. Two datasets are made from MNIST dataset one set contains the digits 0 & 6 and the other set containing 3 & 8. Each of the digits in these sets are divided into three clusters using kmeans clustering algorithm and concatenated with their respective pair. This is done to simulate the different data distributions that the client may have. Now we have two datasets having three sets each, following picture illustrates the same:-  
<p float="left" width="100%">
    <img width="450" height="350" src="https://i.postimg.cc/8zxPD4db/0-6.png">
    <img width="450" height="350" src="https://i.postimg.cc/T1T3FPjM/0-6-2.png"> 
</p>
These two datasets are used to validate the federated SVM
