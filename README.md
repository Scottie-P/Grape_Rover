# Grape_Rover

# Abstract:


#Purpose of the Study: 
Is it possible to record a vineyard row with a video from
a rover and then feed this video through a program that will present the total
grape cluster yield on that row? Can this be done for multiple rows? Can this be
done for an entire vineyard? How helpful would this be for a viticulturist? (The
cultivation and harvesting of grapes, specifically for wine making) Surprisingly;
if they choose to count at all; vineyard managers will hire someone or walk a few
rows themselves, count their clusters, and then extrapolate to the rest of their
vineyard. If they choose not to count, they will use previous data (past years)
to estimate their current fruit yield. With changing weather patterns every year,
this latter technique will only be so useful, and the former method clearly has its
downsides as it only counts a few rows before extrapolating.

Now don’t get the wrong idea, these older processes help get general estimates,
but these estimates will only be so accurate. Getting the best accuracy will help
a vineyard manager better prepare for business contracts. If they oversell their
current tonnage, customers will be upset and won’t do business with them next
year. Therefore, it’s imperative that their customers get the tonnage they expected,
and this requires future planning regarding the total grape count. With modern
technology and all the wonders it brings, it’s easy to assume this would already
be something that has been accomplished, that a rover could drive through a
vineyard and present a total cluster count with some software and algorithm
doing the processing. But if it is being done, only the major players know about
it.

In this paper, the discussion will revolve around what that entails. It will
consider some previous research papers in academia, one particular technique
of isolating objects inside a still image and then using other methods to track
objects as they move through a video. In addition, what would it involve to design
a rover that will accomplish the task of recording a video? Not only will software
be needed to process a video, but some sort of brain or steering system will be
needed to drive the rover around a vineyard to record that video.

#Procedure:
By utilizing the real-time object detection algorithm, YOLO (You
Only Look Once [19]), then one can count grape clusters in an image. This 
algorithm allows one to train a complex neural network with their own classification
objects. Typical examples are recognizing dogs, bikes, or humans. Further, software 
was written on top of identifying images so as to not double count and
recognize new objects entering the frame that have not been seen yet.
This was accomplished with Python scripts to predict object movement by a
self-adjusting momentum vector variable, and then pre-predict its following
location. This network was trained to detect grape bunches, it was not prepared
to detect multiple varieties of grapes, just grapes in general. There’s no reason
one can’t teach a network to recognize different varietals, but that was not this
project’s scope. Furthermore, it needs to be pointed out that only 1287 images
taken in Plymouth California at Belledor Vineyards in August 2021 and were used
to train the YOLO network in this paper. Even with a low number of train/test
images, the results are still impressive. In general, tens of thousands of images
should be used; otherwise, you will more often run into over-counting or 
undercounting grape clusters, which will be discussed further.

In addition, it was decided to create a rover that could capture a video, further
saving time and resources for a vineyard manager, as one would still need to walk
a row to capture the video in order to process a video for a total cluster count.
Implementation: It is helpful to think of this project in a few stages.

1. Train YOLO to isolate desired objects in an image.
2. Implement YOLO with a video, and incorporate some method to count accurately.
3. Create a rover to navigate a vineyard and record a video of said vineyard.

#Conclusions: 
This project involves developing and testing a semi-autonomous
rover that can drive through a vineyard with minimal input parameters. Once it
has finished steering through a vineyard, a grape estimate will be produced using
a trained computer vision algorithm.
Scott will be graduating in May 2022 and hopes that one day the rover will
help growers better estimate their yields while increasing efficiency in vineyard
practices. Scott’s Data Mining class inspired this project in Fall 2019. The course
was instructed by Dr. Shahrad Jamshidi, an advisor to the project, in addition
to Dr. Sudhir Shrestha and Dr. Nansong Wu.
