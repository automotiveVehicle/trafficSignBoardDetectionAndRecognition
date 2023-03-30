# Traffic Sign Board Detection And Recognition

  A vehicle that can sense its surroundings and navigate on its own is called an autonomous vehicle. Autonomous vehicles use a combination of sensors, cameras, and advanced algorithms to collect data about their surroundings and make decisions about where to go and how to avoid obstacles.
  
  Traffic sign board detection is a critical aspect of autonomous vehicle technology. It involves using computer vision and machine learning algorithms to identify and interpret traffic signs in real-time. This allows the vehicle to understand and respond to various road rules and conditions, ensuring safe and efficient navigation.

| <img width="400" height="300" src="https://user-images.githubusercontent.com/79542776/227910492-d0be6e5a-11c6-47da-a858-4988d9d96ee2.png"> |<img width="400" height="300" src="https://user-images.githubusercontent.com/79542776/227911678-c3a93801-2683-42ca-bea9-b1f8446c314a.png"> |Left Prohibited Result|Right Prohibited Result|
| <img width="400" height="300" src="https://user-images.githubusercontent.com/79542776/227910727-c5c1c25f-88e0-4b1d-a195-f2b22f9a3d57.png"> |<img width="400" height="300" src="https://user-images.githubusercontent.com/79542776/227910752-23874b06-5d2c-4869-8662-99ee20154d6c.png">|
|UTurn Result|Three way junction Result|


# Introduction
The traffic sign placed at the side of the roads provides information about route guide,road condition and hazards. In adverse traffic condition the driver may not notice traffic signs which may cause accidents and loss of properties to avoid this many control device has been proposed which alert the driver about the traffic signs.The capability to identify traffic signs and act on them is one of the most important components of a self-driving
automobile.

A traffic sign board detection and recognition system is needed to accurately identifyand interpret traffic signs in real-time, in order to improve road safety and facilitate compliance with traffic regulations. By automatically detecting and interpreting trafficsigns, this system can help drivers to make informed decisions and reduce the likelihood of accidents or violations. Furthermore, a traffic sign detection and recognition system can also provide useful information to traffic management systems and assist with the efficient flow of traffic.

There are several potential advantages to using autonomous cars over traditional cars. First, because they are able to drive themselves, autonomous cars can reduce the need for human drivers and make transportation more convenient and accessible. This is especially useful for people who are unable to drive due to disability or age, and it could also free up time for people to do other things while they are being transported. Second, autonomous cars are likely to be safer than traditional cars because they use advanced sensors and computer algorithms to detect and respond to their surroundings. This can help to prevent accidents and improve road safety, potentially saving lives.

# Functional Block Diagram

![Functional Block Diagram](https://user-images.githubusercontent.com/126253486/227922964-ae2d8913-d776-4cf9-a4f8-20ca6ff66e57.png)

A custom data set of 4 classes is collected and annotated using Makesense.AI. SSD MobileNet model is trained using this data set. The trained model is dumped on Raspberry Pi for real time recognition, through live camera feed input is sent to Raspberry Pi. The annotated output is displayed on the screen.

# Raspberry Pi 3 Model B+ and Raspberry Pi 5MP Camera

## Raspberry Pi 3 Model B+
A credit card-sized, open-source computer board called the Raspberry Pi runs on Linux and many other OS. The Pi is a fun and convenient way for people of all ages to develop their computer and programming skills. The Pi can perform many tasks that a desktop computer can, such browsing the internet and playing videos, by connecting it to a TV or monitor, a keyboard, and the appropriate programs. The Pi is also excellent for creative projects; newer models with more computing power are perfect for Internet of Things projects. Wireless LAN and Bluetooth Low Energy are also included with the Pi 3.

<img width="400" height="300" src = "https://user-images.githubusercontent.com/126253486/228803421-7e2ecb2f-e94f-4769-9159-80273d2e3b79.jpg">


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






