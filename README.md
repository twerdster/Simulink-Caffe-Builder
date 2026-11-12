# Simulink-Caffe-Builder

[![MATLAB / Simulink](https://img.shields.io/badge/MATLAB-Simulink-0076A8)](CaffeLibrary.mdl)
[![Output: Caffe prototxt](https://img.shields.io/badge/output-Caffe%20prototxt-555555)](https://github.com/BVLC/caffe)
[![Status: historical (2015)](https://img.shields.io/badge/status-historical%20%282015%29-lightgrey)](#later-work)

Uses Simulink (Matlab) as a visual builder to generate caffe prototxt files.

![Explanatory illustration: Caffe layer blocks wired in Simulink, simulated to write one text file per layer, then collated into a prototxt file](docs/images/simulink-to-prototxt.svg)

*Explanatory illustration of the workflow in the instructions below. It is not a screenshot of the
Simulink library, and the block names are generic examples.*

> **Repository contents:** the public repository contains `CaffeLibrary.mdl`, the example model
> `Example_3Stage.mdl` and this README. The `collateFiles.m` script described under Instructions is
> not in the repository. This 2015 experiment has not been retested with current MATLAB releases.

### Overview
Building different network architectures in Caffe by hand constructing  
prototxt files is somewhat slow and prone to copy-paste errors.   
Given the wide-spread adoption of Caffe and its very modular layer structure  
it seems reasonable that there should be a visual builder for such files.  
In fact it would be great if there was an integrated visual builder and trainer  
in matlab or Python and each individual layer could be inspected and visualized.  

Towards this goal we have chosen Simulink as a pseudo visual builder.  
It appears that this is not optimal but is sufficient as a first attempt  
towards the goal of a visual prototxt builder.  

### Instructions
* Open simulink in Matlab by typing 'simulink' at the prompt.  
* Use File\Open to open the CaffeLibrary.mdl file.  
* This will bring up the different layers and input types in the CaffeLibrary.  
* Create a new model by going to File\New.  
* In the new model you will need to change the simulation parameters by going to
Simulation\ConfigurationParameters.   
* Change Stop Time to 1. Change Solver Options:Type to Fixed-step. Change Solver to discrete.
Press apply.  
* Now drag and drop items from the CaffeLibrary into your new model and connect
them up in the shape of a network architecture.  
* Once you have connected everything you can press the simulate button.   

If everything works you will see multiple txt files. Currently you need to run the script 
collateFiles.m in matlab and it will collect all the txt files and append
them into one prototxt file. In the future this will happen automatically.  

### Todo
- Create block masks so that input ports can be chosen with drop-down boxes.
- Create a final collation function to automatically spit out the prototxt file.
- Add more layers
- Create known network models (like AlexNet, GoogLeNet, etc) and add them
as library blocks. 
- more ...

### Note
If there is a better graphical builder tool for creating directed graphs
by using drag-and-drop and executing scripts in each graph node then I would be
happy to hear about it. For example a python framework or javascript or something
which can be made to be easily customizable and cross platform without restriction
to using proprietary software.
Also, this is the first time I have used Simulink for anything so its quite likely
the method is not particularly optimal.

### Contribute
Feel free to contribute to this repo. For example more layers will be welcome.
Or even better - an automatic parser that converts caffe's proto file into Simulink
blocks or at least into .m files that can then be used inside the Simulink blocks.

### Later work

A node-based builder of the kind asked for in the note above was later used in Blender:
[Caffe-GUI-Tool](https://github.com/twerdster/caffe-gui-tool), a fork of
[H. Tomkins' original](https://github.com/hctomkins/caffe-gui-tool) extended by Aaron Wetzler and
Rom Hershkovitz. Its maintained continuation for current Blender releases is
[Blender Neural Composer](https://github.com/twerdster/blender-neural-composer).
