## Liter Eliminator ML
This repo is specifically for the Machine learning aspect of the project. The code will include the source code for the models that are needed. 


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

