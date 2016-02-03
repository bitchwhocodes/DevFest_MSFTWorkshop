# DevFest_MSFTWorkshop

DevFest 2016 Microsoft IoT Workshop. Requirements :  Hardware  Sparkfun Weather Shield + Particle Photon, [Visual Studio Code](https://code.visualstudio.com/Download) (free, opensource and available on Mac, Linux, and Windows),  Microsoft Azure account(ACTIVATE YOUR AZURE ACCOUNT USING [DREAMSPARK](https://www.dreamspark.com/Product/Product.aspx?productid=99)), [Node](https://nodejs.org/en/), and [Project Oxford API](https://www.projectoxford.ai/). 

## Project description 

We will be  using the  Particle Photon and Microsoft Project Oxford Emotion API to detect your emotions. Are you anger, contempt, disgust, fear, happiness, neutral, sadness, or surprise?  Before you come to the workshop please make sure to sign up for a free Azure account  using DreamSpark (instructions below), and  Microsoft account so you can access the Project Oxford API. 

##Step 1 Get your Azure Account 

### Activate your FREE Azure Account with DreamSpark 
[![Alt text for your video](http://www.gmlpu.org.uk/wp-content/uploads/2014/10/freestuff.jpg)](https://channel9.msdn.com/Series/Free-Cloud-for-Students/Activating-a-Free-Azure-DreamSpark-Subscription)

Click image to  play video.In this two minute learn how to activate your free Azure account with DreamSpark. 

## Step 2 Sign up for  Project Oxford Emotion API
####What is Project Oxford API?
Project Oxford is a suite of AI APIs from Microsoft and includes APIs around  Vision APIs, Speech APIs, and Language APIs.In this workshop we will be looking at the emotions APIs. 

Emotions APIs detect emotions based on facial expressions.The Emotion API takes an image as an input, and returns the confidence across a set of emotions for each face in the image, as well as bounding box for the face, using the Face API.The emotions detected are anger, contempt, disgust, fear, happiness, neutral, sadness, and surprise. 

![](http://marianaggaga.com/wp-content/uploads/2016/02/emotionapi.png)

1. Go to [Project Oxford site](https://www.projectoxford.ai/)
2. Click get free trial 
![](http://marianaggaga.com/wp-content/uploads/2016/02/start-trial-1.png)
3. Signing with your Microsoft account. 
![](http://marianaggaga.com/wp-content/uploads/2016/02/Microsoftaccount2.png)
4. Show your Emotion API key 
![](http://marianaggaga.com/wp-content/uploads/2016/02/getapikey.png)
5. Copy and paste your key into a notepad for now. 



##[Create a Node.js web app with Azure App Service](https://azure.microsoft.com/en-us/documentation/articles/web-sites-nodejs-develop-deploy-mac/)
Before we build our first Node.js app fork this repo.
###Create a web app in Azure App Service using the Azure Portal
In this section you will learn how to create a web app and enable git publishing 

1. Sign in to the Azure Portal.
2. Click the + NEW icon on the top left of the Azure Portal.
3. Click Web + Mobile, and then click Web app.
  ![](http://marianaggaga.com/wp-content/uploads/2016/02/webapp1.png)
4. Enter a name for the web app in the Web app box.This name must be unique in the azurewebsites.net domain 
5. Select a Subscription (this will be DreamSpark).
6. Select a Resource Group or create a new one.
7. Select an App Service plan/Location or create a new one.

8. Click create

 ![](http://marianaggaga.com/wp-content/uploads/2016/02/webapp2.png)
9. Click Web apps > {your new web app}.
10. In the Web app blade, click the Deployment part.
 ![](http://marianaggaga.com/wp-content/uploads/2016/02/webapp10.png)
11. In the Continuous Deployment -> Click Configure Settings-> click Github
12. Click Github, and then click OK. GitHub will  ask if you want to authorize Azure to have access to your accounts. It's safe to click Authorize application.
13. Select DevFest_MSFTWorkshop GitHub repository from the list and make sure you are deploying the master branch. Click OK 
 ![](https://cloud.githubusercontent.com/assets/3477155/9880464/bea7f6e4-5b99-11e5-9601-f7a6767e32ba.gif)

### Build a Node.js app
This will be covered in the workshop. 
Adding Project Oxford Emotion API to [Project Oxford Web Cam](https://github.com/bitchwhocodes/project-oxford-webcam)

1. Make sure to clone the [Project Oxford Web Cam](https://github.com/bitchwhocodes/project-oxford-webcam)

2. Open routes

3. open main.js file

4. Add your key 

`var oxfordEemotion = require("node-oxford-emotion")(api-key)`

Adding to code to your Spark  Particle Photon board 

1. [Setup Spark Particle Photon board ](https://github.com/LadyNaggaga/DevFest_MSFTWorkshop/blob/master/README.md#getting-started-with-particle-photon-board)
2. Make sure to clone the [Project Oxford Web Cam](https://github.com/bitchwhocodes/project-oxford-webcam)
3. Open project-oxford-webcam-master
4. Go to the sparks folder 
5. Open sparkemotional.ino file.


###Deploy a Node.js application using Git repository.

Now that we have learned to build a Node.js applicaiton that takes

1. Takes a image from your webcam 
2. Uses the Project Oxford Emotion API to sense your emotion
3. Uses the Spark Particle Photon to blink according to the emotion identified 

Let's go a head an deploy your app to Azure 

1. Install Git / if you have go to step 2 
2. Initialize a local Git repository

   `git init`
 
3. Add files to your repo

   `git add .`
   
   `git commit -m "initial commit"`

4. Add a Git remote for pushing updates to the web app that you created in the Create a web app in Azure App Service by using the Azure Portal section

   `git remote add azure [URL for remote repository]`
 
5. Push your changes to 

   `git push azure master`

6. You will be promoted for the user name an password you created earlier Create a web app in Azure App Service by using the Azure Portal section in step 13.
7. To view your app, click the Browse button on the Web App part in the Azure portal.
![](http://marianaggaga.com/wp-content/uploads/2016/02/browse.png)

## [Getting Started with Particle Photon board](https://docs.particle.io/guide/getting-started/connect/photon/)

[How to get started with the Particle Photon board](https://docs.particle.io/guide/getting-started/start/photon/). 

### Prerequisites for Setup
Software Particle Mobile App - [iPhone](https://itunes.apple.com/us/app/particle-build-photon-electron/id991459054?ls=1&mt=8) | [Android](https://play.google.com/store/apps/details?id=io.particle.android.app)

Hardware

1. Your Particle device, brand new and out of the box!
2. USB to micro USB cable (included with Photon Kit and Maker Kit)
3. Power source for USB cable (such as your computer, USB battery, or power brick)
4. Your iPhone or Android smartphone

Wifi Settings

1. 2.4GHz capable router
2. Channels 1-11
3. WPA/WPA2 encryption
4. On a broadcasted SSID network

###Connection your device over USB 

1. [Using Windows](https://docs.particle.io/guide/getting-started/connect/photon/#using-windows)

 - Install the [PARTICLE DRIVER](https://s3.amazonaws.com/spark-website/Particle.zip) It is fine to unzip this as a default into your     Downloads folder.
 
 - Go to the Device Manager and double-click on your Particle device under Other Devices (on Windows 10 your Particle device may be listed under Ports).
 
 - Click Update Driver, and select Browse for driver software on your computer.
 
 - Navigate to your Downloads folder, or wherever you unzipped the drivers.
 
 - The driver is called photon.cat.
 
 ####Install the particle cli

  - In the Command Prompt window, type: `npm install -g particle-cli`

 
2. [Using OSX](https://docs.particle.io/guide/getting-started/connect/photon/#using-osx)

####Install the particle cli

  - Open terminal, type: `npm install -g particle-cli`
  
3. [Connecting your device](https://docs.particle.io/guide/getting-started/connect/photon/#connecting-your-device) 

## Deploy to Azure
[![Deploy to Azure](http://azuredeploy.net/deploybutton.png)](https://azuredeploy.net/)

## Additional Resources 
### [Node.js](https://nodejs.org/en/),[Socket.IO](http://socket.io/) & [Azure](https://www.dreamspark.com/Product/Product.aspx?productid=99)
####Video Resources 
Watch [Stacey Mulcahy]( https://twitter.com/bitchwhocodes) and [Rami Sayar]( https://twitter.com/ramisayar) in this incredibly interesting and entertaining intro to Node.js. 
#####In this video you will learn:
1. [Intro to Node.js ]( https://mva.microsoft.com/en-US/training-courses/building-apps-with-nodejs-jump-start-8422?l=CePazYKz_5504984382)
2. [Intro to Express](https://mva.microsoft.com/en-US/training-courses/building-apps-with-nodejs-jump-start-8422?l=hPPfQZKz_4404984382)
3. [Building a Backend]( https://mva.microsoft.com/en-US/training-courses/building-apps-with-nodejs-jump-start-8422?l=cyMHmZKz_4304984382) 
    [What are web Socket?]( https://mva.microsoft.com/en-US/training-courses/building-apps-with-nodejs-jump-start-8422?l=cyMHmZKz_4304984382)
  [NoSQL Database with MongoDB]( https://mva.microsoft.com/en-US/training-courses/building-apps-with-nodejs-jump-start-8422?l=cyMHmZKz_4304984382)
4. [Creating UI]( https://mva.microsoft.com/en-US/training-courses/building-apps-with-nodejs-jump-start-8422?l=jJXdHaKz_5804984382)
5. [Connecting the UI to the Backend ]( https://mva.microsoft.com/en-US/training-courses/building-apps-with-nodejs-jump-start-8422?l=1nDCeaKz_504984382)
6. [Deploying your app to Azure ]( https://mva.microsoft.com/en-US/training-courses/building-apps-with-nodejs-jump-start-8422?l=xK3w2aKz_9304984382)

####Other Resources 
[Install the Azure CLI tools for Mac, Windows, and Linux](http://blogs.msdn.com/b/cdndevs/archive/2014/09/11/a-chatroom-for-all-part-2-welcome-to-express-with-node-js-and-azure.aspx)

[Create and Deploy a Node App in Azure](https://azure.microsoft.com/en-us/documentation/articles/web-sites-nodejs-develop-deploy-mac/)

[Quick guide to building a Node.js Chat Application with Socket.IO on Azure ](https://azure.microsoft.com/en-us/documentation/articles/cloud-services-nodejs-chat-app-socketio/)

###[Github Getting started with Node.js on Azure ](https://github.com/sayar/NodeMVA)
###[Github Project Oxford Web Cam  ](https://github.com/bitchwhocodes/project-oxford-webcam)   

