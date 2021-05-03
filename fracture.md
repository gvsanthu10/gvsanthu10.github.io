
# Project blig
## _Fracture detection with deep learning_

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)


After years of learning to program and acquiring new technical skills, I finally made it into this. My first blog showing my portfolio.
I started the machine learning journey unconventionally. I had to learn to program, refresh my mathematics and statistics. I enrolled and completed many online courses. Combining all these, this final website is shaping to reflect my skills and ongoing projects. 
## Basics first
Some say machine learning is glorified statistics and I do agree. Machine learning concepts were in practice for a long time and used in academics. Deep learning is a part of machine learning where we use the artificial neuronal network to come to the desired outcome.
I know you find these explanations in thousands of online resources and website, but as with everyone, I will explain this in short.

## A simple prediction model
Imagine you have to guess a number and your friends tells you if you are higher or lower than the expected number.  you randomly guess a number and keep adjusting the number so that you arrive at the final answer. 

![](https://raw.githubusercontent.com/gvsanthu10/gvsanthu10.github.io/master/fracture/1.PNG)



## Machine learning
In machine learning, the algorithm does the same with different equations or different approaches. One approach can be extrapolating the expected outcome or the other can be predicting the outcome similar to the surrounding cases (case with similar characteristics have a similar outcome).

![](https://raw.githubusercontent.com/gvsanthu10/gvsanthu10.github.io/master/fracture/2.PNG)

## Deep learning
Deep learning uses what's called layers of artificial neurons. A single artificial neuron contains an input node, weight and output and some mechanism of feedback. The input is what data we feed in. Output is the prediction. These predictions were compared to the actual outcome and the error is calculated at each cycle.  Weights are updated according to error correction from the output. 

![](https://raw.githubusercontent.com/gvsanthu10/gvsanthu10.github.io/master/fracture/2.PNG)

With layers of these neurons, we get Deep learning.  Sometimes deep learning appears like a black box where you put some input and you get an output. It is difficult to view what is happening inside these layers. However, there is a well-known paper that dissected these layers and showed us what is happening inside. 

[pic]

# My project
I followed fastai tutorials and I applied the concepts and the tutorial to classifying the given Xray to fracture or normal. Fastai is one of the good sources for learning deep learning and they provide video and book-based teaching.

## Intuition

The model (the algorithm) takes up an image of a pelvis Xray AP view and predicts the probability of if there is a fracture of the neck of femur.
## But how it does the magic?

Machines cannot understand what is there in an image. All it knows is the pixel values. Every image has horizontal and vertically packed pixels. Each pixel has a varying number of values about how bright or dark it shows appear when displayed. 
We can extract the data about the arrangement of pixel and correlate with a given outcome, we can predict a fracture.
The pixel data is fed to the deep learning model. The model predicts some outcome initially which is then compared to the actual outcome. It matches then it upregulates a particular weight. If there is an error, it downregulates a particular weight. Over many cycles and reading many images, the model comes with the best accuracy.

## Collection of data
I used bing search API to collect "Normal pelvis X-ray AP view" and "Fracture neck of femur pelvis AP X-ray". Because I am a radiologist, I also broadened the search terms to include sub-capital, subtrochanteric and intertrochanteric fracture to accumulate as many images.

### Increase the number of available images
It is called data augmentation. 
Even if we have a small number of images, we can increase the number by tilting, zooming and wrapping the images so that we get even more images. Machines do not even recognize an image if it is rotated for 1 degree, because the pixel gets rearranged. Data augmentation answers both increasing the available images to train and also make the model recognize tilted or wrapped images.
![](https://raw.githubusercontent.com/gvsanthu10/gvsanthu10.github.io/master/fracture/download%20(1).png)

## Final performance

![](https://raw.githubusercontent.com/gvsanthu10/gvsanthu10.github.io/master/fracture/Capture.PNG)

![](https://raw.githubusercontent.com/gvsanthu10/gvsanthu10.github.io/master/fracture/download.png)

For a fresh starter in deep learning, this is quite impressive. I am proud of my first project. 

# Limitations of my project
When I was appearing for the FRCR exam, I was preparing for "Rapid reporting". In rapid reporting, we had to interpret a radiograph if it is normal or abnormal. Over many days of practice, I noticed that Normal radiographs(X-rays' other name) have perfect exposure, alignment and the films are super clear. The ones with a fracture were taken in weird positions, having a degree of soft tissue oedema and exposure factors were suboptimal. The reason for that is, an examiner can easily get a normal radiograph and he or she picks a good presentable one. When they want a radiograph with a fracture, the number of cases will be limited and they have to pick whatever they have in the hospital PACS library. So, whenever I saw a dirty radiograph, I was always a bit extra careful in detecting a fracture. 
This helped me to score 29.5 out of 30 on my final exam.
What I suspect is that my algorithm is predicting clean radiograph for normal and weird ones a fracture. In the end, a model does not know what a fracture is. It simply associates confounding fractures and assembles everything to come to a prediction.
I used jpg images instead of DICOM images. I do not have access to publicly available DICOM datasets yet.
My model is only trained for detecting a fractured neck of the femur. It does not know about tumours or other pelvic fractures.

# Next Steps
Object detection for localizing the fracture or a central line tube. Object tracing to highlight a central tube. Then finally to predict if a central line is in a good position or not. 
