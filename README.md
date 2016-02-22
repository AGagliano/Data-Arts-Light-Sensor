# Data-Arts-Light-Sensor

This code allows you to log the data you receive from your light sensor on your Kinoma device. The code logs the data into Initial State. https://www.initialstate.com/ <br>
Initial State helps you store your data for Internet of Things (IoT) devices and allows you to quickly view the data in action in real time. <br>
Initial State also allows you to download the data as a .csv file. 



##Step 1

Sign up for a free Initial State account: https://www.initialstate.com/ <br>
Note, the free account only allows logging of 25,000 data points per month. <br>
So, if we log 1 data point from our light sensor every 1 minute then we have about 415 hours of logging time. <br>
Also, the free account only lets you hold your data for 24 hours, so make sure that you complete your mission within 24 hours. <br>

##Step 2

Install Kinoma Studio if you haven't already: http://kinoma.com/develop/studio/

##Step 3

Open up Kinoma Studio and create a new Application Project: File > New > Application Project <br>
Give the project a name and click 'Next>' <br>
Here, you can edit the ID, Title, and Version number. I'd just use the defaults though, so you can click 'Finish' <br>

Your Kinoma Studio should now look like this (note, I titled my application 'Light Sensing Mission'): 
![Alt text](/New.Application_ScreenShot.png?raw=true "Optional Title")

Now, you you'll see the the interface for your application project. This is where we will use wifi to connect your Kinoma device and run your application on the Kinoma. But, more on this to come later, because we need to tell the Kinoma what we even want to do.

We do this with a file called main.js. In this file we use some JavaScript to tell Kinoma which pin number to read analog values as input (in our case this is Pin 53 for the analog pin of our light sensor). We can also use the JavaScript to have all the data we collect sent to Initial State so that we can save it and visualize it. We also use the JavaScript code to change how frequently we collect data. For example, we could collect data every second, once per minute, or once an hour, etc.

To open the main.js file, go File > Open File.. > navigate to the folder name of your project > src > main.js <br>

![Alt text](/emptyjs_ScreenShot.png?raw=true "Optional Title")

Notice the file is empty, so let's populate it with the code in the main.js file that you can find here in this github repository. <br>
Navigate to src/main.js on this github page and copy the code and paste it into your main.js file in Kinoma Studio. <br>

Navigate to main.js in github:
![Alt text](/src_github_ScreenShot.png?raw=true "Optional Title")
![Alt text](/mainjs_github_ScreenShot.png?raw=true "Optional Title")

Highlight and copy the code (lines 1-67):
![Alt text](/copycode_github_ScreenShot.png?raw=true "Optional Title")

Paste the code into the main.js file in your Kinoma Studio: 
![Alt text](/pastecode_ScreenShot.png?raw=true "Optional Title")

Remember to ctrl-s to save the main.js file!

##Step 4

Now, go back to the application.xml file. You'll see a 'Run>' button next to the Kinoma Create. This is our simulator. We can simulate everything we do on the Kinoma on the computer before we ever connect to our real Kinoma. We won't use this functionality now, but it is great for debugging in the future. 

To connect your Kinoma device so we can run all this code on it, we need to connect via WiFi. <br>
So, turn on your Kinoma. 
Click the connect to WiFi button and follow the instructions to connect to a WiFi network. Note, this will not work very well on large public networks (e.g. Airbears or CalVisitor). If you don't have a private WiFi network to connect to, please try tethering your phone (e.g. creating a personal hotspot). 

Make sure your computer is on the same Wifi/hotspot network as the Kinoma. 

Now, back in your Kinoma Studio, if you press the 'Refresh device list' your Kinoma device should populate. You'll notice the 'Run>' button associated with the device. This is what we will press to run the code on our Kinoma (we will come back to this though after we configure with our Initial State account we made). 

##Step 5

Go back to your Initial State account and in the left panel, click the 'Create HTTPS bucket' (it is the one with a + and a cloud symbol). <br>
Give your bucket a name. A bucket is simply a container to hold all the data we will read in from the light sensor on the Kinoma. You can create a new bucket every new session, or keep adding to the bucket. Up to you! <br>
Click 'Create'

##Step 6
Now, we need a way to tell our code in the 'main.js' which will capture our data from the light sensor and send it to this bucket in Initial State that we just created. <br>
The bucket we made has some unique identifiers that we can insert into our main.js to do this. <br>
Go to the 'settings' for the data bucket you just created. <br>
You'll see a 'Bucket Key' and an 'Access Key' <br>
First, copy the bucket key. <br>
Then, go into your Kinoma Studio and look at the main.js file and find the line that says 'var BUCKET_KEY = "YOUR BUCKET ID";' and replace the YOUR BUCKET ID with your pasted bucket id. <br>
Go through this same process for the Access Key line below. <br>
Make sure when the key is pasted into the code that it still has the quotes remaining. Here is an example: 

var BUCKET_KEY = "D7JKXEFXXGJ9"; <br>
var ACCESS_KEY = "TlGImW8S2maMXoqgtfOxvJZ90h82jSOf"; 

(your numbers will be different)

Remember to save once you update the code!

##Step 7

Now, let's get in the right view on Initial State to view your data as we capture it real time. <br>
Click on the new bucket you created. <br>
Then, click on the waves view. <br>
(Note, Initial State may prompt you to go through some tutorials. I would walk through these as they will help you understand the interface)

##Step 8

Back in Kinoma Studio, press the 'Run>' button of your connected Kinoma device. 
Cover your light sensor for a few minutes. <br>
Then, uncover your light sensor for a few minutes. <br>
Then, shine a flashlight on your light sensor for a few minutes. <br>

What do you notice on the waves screen on Initial State? Do you see the data being read each minute? 
(You may need to right click in the left panel of the waves screen and press 'amplify +' to get a closer up view of the data. 
Isn't it beautiful!

##Step 9

Once you've collected all the data you would like to, stop collecting data by pressing 'Stop' in Kinoma Studio. 

##Step 10
Now, in Initial State we can zoom in our data and view it in various ways. Play around with this some and notice what you see. 

##Step 11
Now, to save our logged data, let's download a csv file with all of our minute by minute logged data. 
Click your bucket again. 
Click the source icon. 
In the left most corner is a 'Save as File' download button. This should automatically download a csv file. 
Open up this file in excel and you will see all of the voltage analog values read from the light sensor at each point in time. 






