# Traffic Sign Board Detection And Recognition

  A vehicle that can sense its surroundings and navigate on its own is called an autonomous vehicle. Autonomous vehicles use a combination of sensors, cameras, and advanced algorithms to collect data about their surroundings and make decisions about where to go and how to avoid obstacles.
  
  Traffic sign board detection is a critical aspect of autonomous vehicle technology. It involves using computer vision and machine learning algorithms to identify and interpret traffic signs in real-time. This allows the vehicle to understand and respond to various road rules and conditions, ensuring safe and efficient navigation.

| <img width="400" height="300" src="https://user-images.githubusercontent.com/79542776/227910492-d0be6e5a-11c6-47da-a858-4988d9d96ee2.png"> |<img width="400" height="300" src="https://user-images.githubusercontent.com/79542776/227911678-c3a93801-2683-42ca-bea9-b1f8446c314a.png"> |
|:---:|:---:|
|Left Prohibited Result|Right Prohibited Result|
| <img width="400" height="300" src="https://user-images.githubusercontent.com/79542776/227910727-c5c1c25f-88e0-4b1d-a195-f2b22f9a3d57.png"> |<img width="400" height="300" src="https://user-images.githubusercontent.com/79542776/227910752-23874b06-5d2c-4869-8662-99ee20154d6c.png">|
|UTurn Result|Three way junction Result|


# Introduction
The traffic sign placed at the side of the roads provides information about route guide,road condition and hazards. In adverse traffic condition the driver may not notice traffic signs which may cause accidents and loss of properties to avoid this many control device has been proposed which alert the driver about the traffic signs.The capability to identify traffic signs and act on them is one of the most important components of a self-driving
automobile.

A traffic sign board detection and recognition system is needed to accurately identifyand interpret traffic signs in real-time, in order to improve road safety and facilitate compliance with traffic regulations. By automatically detecting and interpreting trafficsigns, this system can help drivers to make informed decisions and reduce the likelihood of accidents or violations. Furthermore, a traffic sign detection and recognition system can also provide useful information to traffic management systems and assist with the efficient flow of traffic.

There are several potential advantages to using autonomous cars over traditional cars. First, because they are able to drive themselves, autonomous cars can reduce the need for human drivers and make transportation more convenient and accessible. This is especially useful for people who are unable to drive due to disability or age, and it could also free up time for people to do other things while they are being transported. Second, autonomous cars are likely to be safer than traditional cars because they use advanced sensors and computer algorithms to detect and respond to their surroundings. This can help to prevent accidents and improve road safety, potentially saving lives.

# Functional Block Diagram

<img  width="600" height="300" src="https://user-images.githubusercontent.com/79542776/228813917-a64986ec-1957-437d-a39c-4cb0fc159dd3.png">

A custom data set of 4 classes is collected and annotated using Makesense.AI. SSD MobileNet model is trained using this data set. The trained model is dumped on Raspberry Pi for real time recognition, through live camera feed input is sent to Raspberry Pi. The annotated output is displayed on the screen.

# Raspberry Pi 3 Model B+ and Raspberry Pi 5MP Camera

## Raspberry Pi 3 Model B+
<img  align = "right" width="400" height="300" src="https://user-images.githubusercontent.com/126253486/228803421-7e2ecb2f-e94f-4769-9159-80273d2e3b79.jpg">

A credit card-sized, open-source computer board called the Raspberry Pi runs on Linux and many other OS. The Pi is a fun and convenient way for people of all ages to develop their computer and programming skills. The Pi can perform many tasks that a desktop computer can, such browsing the internet and playing videos, by connecting it to a TV or monitor, a keyboard, and the appropriate programs. The Pi is also excellent for creative projects; newer models with more computing power are perfect for Internet of Things projects. Wireless LAN and Bluetooth Low Energy are also included with the Pi 3.

### Specifications :-

• Processor:-Chipset BCM2387 from Broadcom Bluetooth 4.1 and 802.11 b/g/n Wireless LAN on a 1.2GHz quad-core ARM Cortex-A53 processor (Bluetooth Classic and LE)

• GPU :- Multimedia coprocessor with dual core and VideoCore IV. offers 1080p30H.264 high-profile decoding, hardware-accelerated OpenVG, and Open GL ES 2.0. capable of 24GFLOPs, 1GFLOPs, or 1.5Gtexels per second with DMA architecture and texture filtering.

• Memory :- 1GB LPDDR2

• Operating System :- Boots off a Micro SD card and launches a version of Linux or Windows 10 IoT.

• Dimensions :- 85 X 56 X 17mm

• Power :- Micro USB socket 5V1, 2.5A

## Raspberry Pi 5MP Camera
### Specifications:-
<img  align="right" width="300" height="200" src="https://user-images.githubusercontent.com/79542776/228799483-5e93651a-08e5-44c4-a773-4b3ce368a276.png"> 

• 5mp 

• 2592x1944 pixels 

• 1080p 30fps,720p 60fps,640x480p 90fps 

# Data Set
We have collected customised data set. We have chosen four classes , two from mandatory traffic sign and two from caution traffic sign:-

1.Left Prohibited

2.Right Prohibited

3.U turn

4.Three way Junction

We have collected 256 images of each class total of 1025 images in which 820(80%) is used for training , 102(9.95%) is used for validation and 103(10%) is used for testing.

# Annotation
<img  align="right" width="300" height="200" src="https://user-images.githubusercontent.com/79542776/228805835-34a5c623-27d3-492a-b34e-5e723aaa3d87.png"> 

• Annotating digital photographs is a task that normally requires human input and, in some situations, computer assistance.

• As in this project we use 4 different traffic signs of 1025 images we label each of these images for training the model.

• For data-set annotation there are many open source like Labelimg, Labelbox, MakeSense.

• In this project we are using MakeSense.AI. It is open source used for image annotation.

• Annotated images will be exported in xml format. xml file is converted into data file format called TFRecords which is used by TensorFlow for training .

# Model
We have selected SSD MobileNet over Faster R-CNN and yolo as it has faster response time in raspberry pi , less usage of memory and as small objects can not be detected in yolo.
## SSD MobileNet
• In 2016, the Single Shot MultiBox Detector, a method for item detection in photos using a single deep neural network, was released.
   
• Single shot object detection, or SSD, uses a single shot to find and identify several objects in a picture.
   
• The detection box is predicted using multi-reference techniques using a group of anchor boxes with various sizes and aspect ratios defined at various positions in the image.    
   
• Streamlined architecture that is simplified An effective approach for mobile and embedded vision applications is provided by Mobilenet, which builds lightweight    deep convolutional neural networks using depthwise separable convolutions.        
   
• It will calculate a total of 3000 bounding boxes.
   
• Further filter out bounding boxes using non-maximum suppression
   
• Non-maximum suppression will match the predicted boxes to the input give ground truth boxes and remove all the duplicates and keep one box which has higher accuracy.

### Specification Of Model

 #### VGC16:-
• VGG16 is used by SSD to extract feature maps. Then, an 8X8 spatial resolution object detection using the Conv4_3 layer is performed (it should be 38X38).

• A bounding box and 21 scores for each class make up each prediction (one extra class for no object).

• The highest score of the class for the bounded object. Totally 38 X 38 X 4 predictions are made by Conv4_3.

• SSD reserves the class "0" to denote that it does not have any objects.

#### Extract Feature Layers:-
1.Multi-scale feature maps for detection:- After the VGG16, SSD adds six more auxiliary convolution layers. For object detection, an additional five of them will be
added. In three of those layers, we make six predictions as opposed to four. In total, SSD employs 6 layers and generates 8732 predictions.

2.Default boundary box:- With just one prediction per default box, SSD restricts the number of default boxes to 4 or 6.

3.Choosing default boundary boxes:- Each feature map layer in SSD has a scale value specified. Conv4 3 identifies things at the smallest size of 0.2 starting from
the left.

4.Matching strategy:- Positive matches and negative matches are two categories for SSD predictions. The localization cost for SSD is only calculated using positive
matches.

5.Hard negative mining:- Positive matches are far outnumbered by bad matches. A class imbalance results from this, which is bad for training.

6.Data augmentation:- Enhancing data is crucial for increasing accuracy. Add flipping, cropping, and colour dithering to the data.

#### Specifications:-
• Weight=0.00004

• Classification weight 1

• Localization weight 1

• IOU threshold 0.6

• Number of steps 1000000

• Batch size 16

• Epochs 6250

# TensorFlow Lite
• Google created the open source machine learning framework called TensorFlow. It is commonly used for training and building ML and DL models. It uses
variety of algorithms.

• One key advantage of TensorFlow Lite architecture is its ability to run on wide range of platforms including CPUs, GPUs and TPUs.

• TensorFlow Lite models can run quickly and efficiently on mobile devices without sacrificing accuracy.

• Tensorflow offers a variety of operations for machine learning applications across various sorts of datasets, including object detection, object segmentation, and even text spell checking and pattern recognition.
