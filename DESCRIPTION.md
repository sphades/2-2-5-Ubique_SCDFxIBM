
# Ubique

[As one of the world's smartest cities](https://www.edb.gov.sg/en/news-and-events/insights/innovation/what-it-takes-to-be-a-smart-city-in-southeast-asia.html), Singapore looks set to have an increasing number of IoT-enabled devices. Ubique is an early warning system empowered by machine learning and cloud services. Ubique takes advantage of many diverse IoT devices around us, including CCTVs, environment sensors and power usage sensors. With this wealth of information, Ubique provides accurate predictions on emergency incidents, advising the emergency services on appropriate actions to optimize efficiency of scarce emergency resources. 


## Ultimate Goal of Ubique
Every single possible sensor, camera, any IoT devices connected to our system. Using the information collected, Ubique will be able to detect any form of emergency incidence with machine learning and trigger early intervention measures to deal with them. 

## Current Problems with Emergency Responses

### 1. Slow Detection Time
Upon detection of a fire, emergency response is undoubtedly fast and efficient. However, one often overlooked area is the detection time of a fire. A [research](https://www.epsu.org/sites/default/files/article/files/6367-Its-about-time-LOW-RES2.pdf) by the Fire Brigade Union in the UK found that the spread of fire is exponential. This means that the size of fire doubles every minute and thus, failure to detect it quickly can lead to catastrophic results. This is evident from cases in Singapore where electrical fires occurred in the wee hours everyone is asleep. By the time the fire was detected, significant damage had been done to the property. Thus, if we can reduce the detection time of fire, significant damage on property and lives can be prevented.
### 2. False Positives/Alarms
There are many instances of reports made to the SCDF where people mistake fogging smoke or haze as smoke emitted from fires. As a result, emergency resources deployed to such false positives are wasted. Furthermore, smoke detectors and other pre-existing fire detection tools may give false alarms. For instance, smoke from cigarettes can trigger a smoke detector leading to a fire alarm. Thus, if multiple sources and sensors can be used to check for the occurrence of such events, the accuracy of alarms will be significantly increased.
### 3. Overreaction to incidents
The response to an emergency should be proportionate to the scale of its severity. For instance if there is a small fire that can be easily extinguished with a fire extinguisher, a fire engine should not be deployed. More often than not, such occurrences may occur due to inaccurate fire reports where the reporter of the fire exaggerates the situation. As a result, needless panic is induced and precious resources are wasted. Thus, if the severity of the incident can be more accurately determined, more informed and evidence-based decisions can be made.

## Features of Ubique
### 1. Reduction of incident detection time
By constantly analysing data collected from CCTVs and environment sensors using its machine learning capabilities, Ubique can quickly detect any instances of an emergency without the need of any human intervention. It can then decide to relay important information to Community First Responders (using software like Twilio) and the SCDF ops centre for immediate actions and appropriate decision making based on the severity of the situation. With Swift and decisive actions being taken, damage to property and loss of lives can be significantly reduced.



### 2.Determine the accuracy of incident reports made 
When incident reports are made, data from sensors linked to Ubique at the location will be analysed and cross referenced to verify the accuracy of the report.  For instance machine learning tools like visual recognition can be used on footage of the camera at the scene to detect if there is a fire. Other data from sensors like thermometers and humidity sensors at the scene will be analysed and crossed-referenced with data from previous fires to accurately determine if the report is indeed true.  

### 3.Determine the severity of the incident
With the help of its sensors and machine learning capabilities, Ubique will be able to determine how severe the emergency is and decide a response proportionate to its severity. For instance, it can identify the size of the fire or number of casualties from the cameras and provide such information to the SCDF Ops Centre so that they can allocate sufficient resources to deal with the problem.


## Implementation

### Input

Ubique takes data from multiple sources, but for demonstration purposes, we have used IBM's IoT Platform and Webcam input to illustrate how such input data can be processed. For this sample flow, we ilustrate how sensor data can be used to analyze if there is a fire, and if so, to activate early intervention measures (e.g. sprinklers, activation of fire shutters).

### IBM Internet of Things Platform 

A simulation of IoT ([available on IBM's website](http://quickstart.internetofthings.ibmcloud.com/iotsensor)) was initialized to act as a sample of how IBM's IoT platform, if integrated into the target areas (e.g. buildings), could be used to provide sensor data to feed into Ubique. In the context of a fire, temperature of a room would increase and the humidity will drop, and such data will be fed into Node-RED to analyze for the presence of a fire and consequently the activation of relevant measures. 

This platform could be further expanded - for example, object detection could be added to live video feeds for live detection of growing fires, which would activate sprinklers within a certain beyond a set threshold, or for the automatic closing of vehicle lanes/broadcasting of such information in the event of an accident. 

### Visual Feed

A webcam image input was used to simulate CCTV input. With images being captured by the visual feed, they will be transmitted to the Visual Recognition service (part of Watson Studio), with the AI analyzing the contents of the picture. If certain keywords/scores are met (e.g. keyword 'fire' appears), the flow of information continues.

 Expansion of the project could entail the usage of Machine Learning, to further process the data provided along with any false positives to automatically improve upon detection accuracy. Ubique could also be combined with the myResponder app to automatically alert nearby Community First Responders, upon visual detection of any cases in which they can assist (e.g. falls).
#

## Node-RED

Node-RED facilitates the flow of information between different devices and services. In the case of Ubique, it is integral in acting as a bridge between information and action.

In this case, a function filters the information transmitted from the sensors and analyzes the possibility of there being a fire. If the system analyzes a fire, an output would be initiated. For our example, the Twilio API is used to send a text message to the end user (e.g. building manager) that there is/could be a fire. 

In future, given a larger dataset, and when scaled up to an IoT-enabled area, the output could be the activation of fire sprinklers in the area, the automatic closing of fire shutters, along with an alert system. This could be done based upon the information gathered from other sensors, even if a small fire is detected but with the potential to become a disaster.

#
## Conclusion

As it's name suggests, Ubique has the potential to be everywhere in an IoT-enabled environment. It is not just an app - it is a concept. There are many areas to expand upon what we have currently illustrated. The potential of Ubique is limitless. Yet at it's core, it is just a simple idea - to leverage on what is available to help organizations better manage their limited resources. 

## Acknowledgments

Nullam nec lectus massa. Proin feugiat placerat nisi lacinia lobortis. Duis efficitur ac orci ac lobortis.
