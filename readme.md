## Liter Eliminator ML
This repo is specifically for the Machine learning aspect of the project. The code will include the source code for the models that are needed. 

#### Creating a Haar Cascade Classification Model:
The model was created using a pre-built application called Cascade Trainer GUI.
https://amin-ahmadi.com/cascade-trainer-gui/
Through this application, a lot of time is saved. It allows experimentatio with a model without having to fully implement it yourself. The drawback is relativly low custimization of the model. However as always, a great amount of time is required to collect training data.
To run the program, a directory for positive images(images containg the desire object) and a directory for negative images need to be specified. Sometimes the paramter "Positive Image Usage" must be decreased otherwise the model will throw errors in trianing. This is due to insuficient amount of training data

#### Running yolo V5 model
First this repo should be cloned into a directory. Run the initial commands in the jupyter notebook to install the required dependencies as well as cloning the yoloV5 directory. Retraining the model is not necessary, the best_yoloN.pt or best_yoloS.pt are models that were created after running the training command. One of the models need to be placed in the runs/predict directory of the yolov5 repo in order for prediction function in the jupyter notbook to work. Last, a path to one of the training phots should be specified. This photo can then be used for prediction when calling the inference() function. The output should be visible when calling the visualize() function. 



### For Continuity, information below is retained, but only relevant to the pre-alpha build Milestone

#### Dependencies:
From current research, "pytorch" will be the base package of the project. However, there are packages like "Detecto" that provide an abstraction layer above pytorch. Part of the abstraction is a standardized approach for training models for object detection.  "detecto" allows for much simpler and condensed code, but sacrifices customization capability and performance in some cases.

#### Expected problems/dificulties
For the end of semester prototype, "detecto" would work sufficiently for a normal camera using static trash detection in the lab. Static detection refers to a non-moving camera, and normal refers to standard FOV. Our final design will mount a 360 degree camera to a moving robot (Example shown below).

![exp360](https://user-images.githubusercontent.com/73602353/228676446-5716ff4f-1243-4722-bfc6-3d55f859496c.jpg)

Objects near the edges of the camera will be distorted. Standard "detetecto" models for training will likely cause many misclasifications when live test data coming from the camera is used. Research has already been conducted in this area(link attached below). To integrate their models, more bare-bones pytorch frameworks will be needed. Another option is to try and capture training images from the camera instead of a standard camera. 

#### Demo ML models 

A tutorial using "detecto" showed off simple framworks of a pretrained model. It used a pretrained model that can detect up to 100 objects. 
Output using a standalone image as input:
![output](https://user-images.githubusercontent.com/73602353/228676340-97e6fda4-68de-4361-b8fd-541a7e8fc86f.png)

Next, I followed the tutorial to train a large dataset as well as making minor improvments to the model. I used Google Colaboratory for the heavy computation, but for later training on our model, I will use my HyperGator acess (through my ML class). 
I tried to use Hypergator first, but I ran into problems trying to install the "detecto" package onto the server. PIP installs are not viable since they are dangerous in Conda environments(risk of breaking entire envirnment). I also struggled trying to import the dataset into hypergator. Furthor research/contacting HyperGator help is needed. Next semester I will either need to reapply or use Google Colaboratory feature again.  

#### Rough Estimation of work

General Preliminary research/Speaking with ML professor ~ 3 hours

Research pytorch documentation ~ 1 hour

Research detector documentation ~ 1 hour

Complete Basic excercises using detector ~ 4 hours

Research Hypergator functionality ~ 2 hours


#### Documentation/Refrences

https://detecto.readthedocs.io/en/latest/

https://towardsdatascience.com/build-a-custom-trained-object-detection-model-with-5-lines-of-code-713ba7f6c0fb

https://ieeexplore.ieee.org/document/8683093

https://anaconda.org/conda-forge

https://help.rc.ufl.edu/doc/UFRC_Help_and_Documentation

