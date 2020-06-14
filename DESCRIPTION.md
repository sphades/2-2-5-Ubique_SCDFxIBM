
# Ubique

[As one of the world's smartest cities](https://www.edb.gov.sg/en/news-and-events/insights/innovation/what-it-takes-to-be-a-smart-city-in-southeast-asia.html), Singapore looks set to have an increasing number of IoT-enabled devices. Ubique aims to leverage upon the data available from such IoT-enabled devices, located all around us, to better allocate limited resources in the case of emergency incidents. This allows for the triggering of early intervention measures, preventing problems from worsening, and consequently resolving the need for activation of emergency resources.

[Project Website](https://code-and-response.github.io/Project-Sample/)
#
## Current problems with current emergency response

### 1. Slow Detection Time

### 2. False Positives/Alarms

### 3. Overreaction to incidents

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
