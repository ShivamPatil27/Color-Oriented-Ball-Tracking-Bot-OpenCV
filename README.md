# Color-Oriented-Ball-Tracking-Bot-OpenCV

A project based on color oriented ball tracking using OpenCV and Python 3.5
 
The camera module of the raspberry pi takes images frame by frame. The crucial thing to be taken care while detecting images frame by frame is to avoid any type of frame drops as then the bot can go into a limbo state if the bot is unable to predict the direction of ball after few frame drops and after background  subtraction. Even if it is able to manage the frame drops but the ball goes out of scope of the camera, it will again into a limbo state. In that case, the bot will take a 360 view of the surrounding and travel in random directions till the ball comes in the scope of the camera and then it starts moving in its  direction. The colour which is to be detected is red colour.

For the image analysis, OpenCV software is used as it has various options for Image editing, detection and masking of image etc. Here we are taking each photograph frame by frame and masking each frame  with red colour. You can hard code any colour you want. Then for noise reduction, excessive noise is eroded and major blobs are dilated with the help of open CV libraries. Then we are returning the mask with reduced noise. After that we will find the contours of the red image object and find the largest of all the contours and bound them in the form of a rectangle. This rectangle will be shown on the main image and then after finding the coordinates of the centre of the rectangle the bot will finally bring the coordinates of the ball to the centre of its imaginary axis and the LED will glow proving that the red coloured ball is detected.

There is a fixed dimension(length and breadth)set for the rectangle which means that if the dimensions of the ball is greater than the dimension of the rectangle in a particular image frame then that red coloured image will be discarded and the LED will not glow. This ensures that only red coloured circular type object is selected and not any red coloured thing.

If there is a situation in which the bot is unable to detect the ball or it is too far from the range then our bot will take that direction for search where the red coloured ball was previously detected by it. Also if there arises a situation in which the ball is too far way and the bot  detects something in front of its path it will  avoid it and reaches its final destination and glows up the LED.

Contour formation and erosion concept is possible only in Open CV which helps in detecting any object. Open CV uses the concept of Masking the image frame by frame which is error free and can be used easily for image detection . This is the extent of vastness which Open CV gives.

# BACKGROUND SUBTRACTION 

Foundation subtraction is a computational vision procedure of separating closer view objects in a specific scene. A frontal area article can be depicted as an object of consideration which helps in lessening the measure of information to be handled and also give essential data to the assignment under thought. Frequently, the closer view item can be considered as a reasonably moving article in a scene. We should underline the word cognizant here on the grounds that if a man is strolling before moving leaves, the individual structures the forefront object while leaves however having movement connected with them are considered foundation because of its dreary conduct. Sometimes, separation of the moving question additionally shapes a premise for it to be viewed as a foundation, e.g if in a scene one individual is near the camera while there is a man far away in foundation, for this situation the close-by individual is considered as closer view while the individual far away is disregarded because of its little size and the absence of data that it gives. 

Distinguishing moving articles from a video grouping is a major and basic undertaking in numerous PC vision applications. A typical methodology is to perform foundation subtraction, which distinguishes moving articles from the bit of video edge that varies from the foundation model. Foundation subtraction is a class of strategies for portioning out objects of enthusiasm for a scene for applications, for example, observation.

The reason for our work is to get a continuous framework which functions admirably in indoor workspace sort of environment and is autonomous of camera situations, reflection, enlightenment, shadows, opening of entryways and other comparable situations which prompt blunders in frontal area extraction. The framework ought to be vigorous to whatever it is given in its field of vision and ought to have the capacity to adapt to every one of the elements adding to incorrect results. Much work has been done towards getting the most ideal foundation model which works continuously. 

Most primitive of these calculations would be to utilize a static casing with no frontal area object as a base foundation model and utilize a straightforward limit based edge subtraction to acquire the closer view. This is not suited for genuine circumstances where ordinarily there is a great deal of development through messed regions, objects covering in the visual field, shadows, lighting changes, impacts of moving components in the scene (e.g. influencing trees), moderate moving questions, and protests being presented or expelled from the scene.

# SHOT BOUNDARY DETECTION

The premise of any shot limit location technique in a video arrangement comprises in distinguishing visual discontinuities along the time space. Amid this identification process, it is required to remove visual elements that measure the level of closeness between edges in a given shot. This measure, signified as g(n,n+k), is identified with the distinction or irregularity between outline n and n+k where k≥1. There exist diverse techniques for registering the estimation of g(n,n+k) in a video succession, being one of the least difficult the supreme contrast between edges.

# MOTION SEGMENTATION

The motion of the video get from the moving objects. Recognition is a procedure of affirming the position of an article with respect to its environment'. This post talks about the ideas included and the execution of Motion Detection in a video utilizing Open CV and C++, as actualized in the specimen code in OpenCV tests envelope, "motempl.c" .here are a few methods for executing movement discovery utilizing Open CV. A standout amongst the best techniques is by utilizing 'Movement Templates'. This strategy was designed in the MIT Media Lab by Bobick and Davis. This strategy is exceptionally valuable in discovery movement in a video. The essential component of this strategy is that movement can be recognized even in little locales of an edge.

# For installing OpenCV on RaspberryPi 3 or 3B+

https://www.pyimagesearch.com/2017/09/04/raspbian-stretch-install-opencv-3-python-on-your-raspberry-pi/

# STEPS
After installation of all the necessary libraries, copy the code onto the directory of ur choice and go to the terminal of your rpi and run the code: python3 project.py

# Note:
Use VNC Server for remote connection to the rpi using Wifi or LAN cable
ALso keep in mind that GPIO pins must be activated along with rpi cam support before running the code
The polarities of tires on the bot must match in configuration with the schematic so that bot runs properly


