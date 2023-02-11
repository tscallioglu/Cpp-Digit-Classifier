# Handwritten Digits Multiclass Clasifier
This is the implementation of CNN  computer vision model to classify handwritten digits in images from the Fashion MNIST dataset, using the Pytorch C++ frontend.<br>


## Usage

### 1. Build
Please build the source file according to the procedure. 
~~~
$ cd build
$ cmake ..
$ make
$ cd ..
~~~

### 2. Cross-Platform Installation
Additional libraries to run the program.
~~~
1. Python 3.9.13 is needed to run the script to download the dataset into the "data" folder. 
   $ cd scripts
   $ python3 download_mnist.py
2. Pytorch C++ (libtorch) 2.0.0.dev20230116+cpu library is needed.  You can follow the instructions from the official Pytorch web site: https://pytorch.org/cppdocs/installing.html . It is needed to be changed  `/path/to/libtorch` in the CMakeLists.txt to the path to the unzipped _LibTorch_
3. OpenCv 4.0.1 is needed. You can follow the instructions from the official OpenCv web site: https://docs.opencv.org/4.x/df/d65/tutorial_table_of_content_introduction.html. 
~~~


### 3. Dataset

- THE MNIST DATABASE of handwritten digits<br>
This is the dataset of 28x28 grayscale for handwritten digits in 10 classes that has a training set of 60000 images and a test set of 10000 images.<br>
Link: [official](http://yann.lecun.com/exdb/mnist/)

Class names are:
~~~
0
1
2
3
4
5
6
7
8
9
~~~



### 4. Run
Please execute the following to start the program at the "build" folder:
~~~
$ ./classifier
~~~

After (by default 10, you can change the number of epochs from kNumberOfEpochs (line 26) variable in the main.cpp) epochs of training, the program asks you to predict new photos in the "pic" folder:
== Input image path: [enter Q to exit]
../pic/0001.png
The digit in the image is  1
[ CPULongType{1} ]
== Input image path: [enter Q to exit]


If the program can not find or load the image, it will give an error:
== Input image path: [enter Q to exit]
../pic/1.png
Can't load the image, please check your path.
== Input image path: [enter Q to exit]


## RUBRIC POINTS

### README 
All rubric points are done.

### Compiling and Testing
All rubric points are done.

### Loops, Functions, I/O

The project demonstrates an understanding of C++ functions and control structures. 
LoadImage (line 32), train (line 82), test (line 112) are functions. There are for loops (line 91-108, 121-132 ...), if else/if conditionals (line 100-107, 146-152 ...). 

The project reads data from a file and process the data, or the program writes data to a file. 
The project reads the training data (line 158) and testing data (line 166) from "data" folder. Also for predictions it reads the im age file in the "pic" folder by using LoadImage function. (line 190)

The project accepts user input and processes the input.
The project reads the input data, file name (line 186) from console to predict the given name of the image.  

### Object Oriented Programming

Classes follow an appropriate inheritance hierarchy.
"struct Net" is derived from "torch::nn::Module". (line 50)

Overloaded functions allow the same function to operate on different parameters.
"forward" function of "struct Net" is overloaded. (line 63)

### Memory Management
The project makes use of references in function declaratons.
In the "LoadImage" function, "train" function, "test" function, references are used.



