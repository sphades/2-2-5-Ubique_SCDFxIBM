## CallForCode2020

![Ubique Icon](/assets/icon.png)  

# Group Name: 2+2=5

## Contents

1. [Short Description](#short-description)
1. [Pitch Video](#pitch-video)
1. [Solution Architecture](#solution-architecture)
1. [Long Description](#long-description)
1. [Project Roadmap](#project-roadmap)
1. [Getting Started](#getting-started)
1. [Using Ubique](#using-ubique)
1. [Live Demo](#live-demo)
1. [Built With](#built-with)
1. [Authors](#authors)
1. [Acknowledgments](#acknowledgments)

## Short description

### What's the problem?
Singapore is facing the problem of an [ageing population](https://www.population.sg/articles/singapores-silver-age), which also results in the decline of workforce participation, a problem the SCDF faces as well. Limited manpower in the SCDF, combined with limited equipment and emergency vehicles, combined with a [rise in fire incidents and EMS calls as shown in 2019](https://www.scdf.gov.sg/docs/default-source/scdf-library/amb-fire-inspection-statistics/scdf-annual-statistics-2019.pdf), means that it is imperative emergency resources are as efficiently channeled as possible. 

### How can technology help?
The rise of internet-enabled devices brought about by the Internet of Things (IoT) means that relevant parties (e.g. SCDF) have greater access to an increased breadth and depth of data from IoT-enabled devices. These parties can leverage upon the wealth of information provided to initiate rapid initial responses upon the onset of disasters, intervening in these incidents before they become more severe, thereby reducing the likelihood of such small incidents from escalating in severity.

### The idea
Ubique is an early warning system empowered by machine learning and cloud services. Ubique takes advantage of many diverse IoT devices around us, including CCTVs, environment sensors and power usage sensors. With this wealth of information, Ubique provides accurate predictions on emergency incidences, advising the emergency services on appropriate actions to optimize efficiency of scarce emergency resources. 

Ubique obtains information from multiple sensors, utilizing artificial intelligence services to filter out relevant data. Ubique then utilizes Node-RED to combine the information available, running it through pre-set criterias and determines the action taken. If an action is necessary, Ubique will intelligently trigger an appropriate alert to involve stakeholders and emergency resources when required. 

## Pitch Video

[![Watch the video](/assets/thumbnail.png)](https://youtu.be/a3U3LXrHAas)

## Solution Architecture

![Diagram of Workflow](/assets/workflow/workflow.png)

1. Input is captured from an image-capturing device (e.g. CCTV, webcam).
2. Images are sent for Visual Recognition Processing.
3. IBM Internet of Things (IoT) Platform receives data from connected devices.
4. Node-RED further processes data from IBM IoT Platform and processed data from Visual Recognition Processing determining if the situation calls for the user to be informed.
5. User (SCDF) receive information about potential emergencies, allowing them to trigger early intervention measures.

## Long Description

[More details are available here](DESCRIPTION.md)

## Project Roadmap

[More details are available here](ROADMAP.MD)

## Getting Started

### Cloud Installation (Recommended)

1. Follow the instructions provided by IBM for [Creating a Node-RED Starter Application](https://developer.ibm.com/components/node-red/tutorials/how-to-create-a-node-red-starter-application/).  
2. Open your Node-RED Application  
3. Navigate to Menu --> Manage Palette --> Install  
![Install Packages](/assets/install/menu1.png)  
4. Key in the following packages in the search bar individually and install them:
![Settings](/assets/install/settings.png)  
```
node-red-contrib-browser-utils
node-red-contrib-image-output
node-red-contrib-scx-ibmiotapp
node-red-node-twilio
```
5. Close the User Settings Page
6. Open the Menu --> Import --> ![](/assets/install/import.png)  
![Import](/assets/install/menu2.png)  
7. Navigate to /assets/install and select the flow.json file.
8. Press the Import button
9. Deploy!
***

### Local Installation 

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. 

### Prerequisites

Software required

- [Git](https://git-scm.com/downloads)
- [Node.js](https://nodejs.org/en/download/)

Setup required

- [Twilio](https://discourse.nodered.org/t/send-twilio-sms-with-node-red/9613)
- Node-RED

Once the software have been installed, open CMD/Terminal/bash and key in the following command to install Node-RED:
```bash
npm install -g node-red
```

### Installing

Navigate to the desired directory where you would like your app to be located.

In a terminal window, clone the node-red-app git repository:
```bash
git clone https://github.com/IBM/node-red-app.git
```

Install required packages for Ubique's Node-RED Flow:
```bash
npm install node-red-contrib-browser-utils
npm install node-red-dashboard
npm install node-red-contrib-image-output
npm install node-red-contrib-scx-ibmiotapp
npm install node-red-node-twilio
```

Launch the Node-RED server
```
node-red
```

In your browser, navigate to ```http://localhost:1880```.

Follow steps 3-8 from Cloud Installation above.

Deploy!

## Using Ubique

### Setup

1. Open up your instance of Node-RED.
2. Launch [IBM's IoT Simulator](https://quickstart.internetofthings.ibmcloud.com/iotsensor/).
3. Record down the device ID at the top right of the page.  
![IoT](/assets/use/iot.png)
4. Double click the IBM IoT node and input your device ID recorded in step 2 in the Device ID field.  
![Node-RED IoT Node](/assets/use/node-red-iot.png)
5. Double click a twilio node and input your phone number in the To field.
![Twilio Node](/assets/use/twilio.png)
6. Deploy!

### Testing
In this test case, we will be using an image of fire to simulate the detection. 
![By (Photograph used by permission of the USDA Forest Service.) - Bunk S: World on Fire. PLoS Biol 2/2/2004: e54. doi:10.1371/journal.pbio.0020054.g001, CC BY 2.5, https://commons.wikimedia.org/w/index.php?curid=1370864](/assets/use/fire.png)

1. Click the yellow button beside the file inject node and upload the picture of fire above.
2. If the system has been set up properly, the number you had earlier set in the twilio node should receive an SMS. 

## Live Demo

You can find a running system to test at [https://ubique.mybluemix.net/red](https://ubique.mybluemix.net/red).

## Built with

* [Node-RED](https://nodered.org/) - The main platform used to link multiple services together
* [IBM Watson Studio](https://cloud.ibm.com/catalog/services/watson-studio) - The AI platform for processing image data
* [IBM Cloud Foundry](https://cloud.ibm.com/cloudfoundry/overview) - The PaaS service used to host the app
* [IBM Internet of Things Platform](https://cloud.ibm.com/catalog/services/internet-of-things-platform) - The AI platform providing the visual recognition service 
* [Twilio](https://www.twilio.com/) - The communications platform used to alert the end-user

## Authors

* **Symus Say**
* **Wong Wai Chung**
* **Nicholas Tan**

## Acknowledgments

* Based on [Billie Thompson's README template](https://gist.github.com/PurpleBooth/109311bb0361f32d87a2).
* Based on [IBM's README template for Call for Code 2020](https://github.com/Code-and-Response/Project-Sample).
* Images and icons sourced from [IBM](https://cloud.ibm.com/catalog) and [Wikimedia Commons](https://form.gov.sg/#!/5eb0b5e85ef87a00115647d7).