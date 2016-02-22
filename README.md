# Data-Arts-Light-Sensor

This code allows you to log the data you receive from your light sensor on your Kinoma device. The code logs the data into Initial State. https://www.initialstate.com/
Initial State helps you store your data for Internet of Things (IoT) devices and allows you to quickly view the data in action in real time.
Initial State also allows you to download the data as a .csv file. 

##Step 1

Sign up for a free Initial State account: https://www.initialstate.com/
Note, the free account only allows logging of 25,000 data points per month. 
So, if we log 1 data point from our light sensor every 1 minute then we have about 415 hours of logging time. 
Also, the free account only lets you hold your data for 24 hours, so make sure that you complete your mission within 24 hours.

##Step 2

Install Kinoma Studio if you haven't already: http://kinoma.com/develop/studio/

##Step 3

Download the main.js file in this repository and put them in a folder on your computer. This should include 'application.xml' and the 'src' folder which contains the 'main.js' code. 

##Step 4

Open up Kinoma Studio and open both the 'application.xml' and 'main.js' files that you just downloaded.

##Step 5

Go back to your Initial State account and in the left panel, click the 'Create HTTPS bucket' (it is the one with a + and a cloud symbol). 
Give your bucket a name. A bucket is simply a container to hold all the data we will read in from the light sensor on the Kinoma. You can create a new bucket every new session, or keep adding to the bucket. Up to you!
Click 'Create'

##Step 6
Now, we need a way to tell our code in the 'main.js' which will capture our data from the light sensor and send it to this bucket in Initial State that we just created. 
The bucket we made has some unique identifiers that we can insert into our main.js to do this. 
Go to the 'settings' for the data bucket you just created.
You'll see a 'Bucket Key' and an 'Access Key'
First, copy the bucket key. 
Then, go into your Kinoma Studio and look at the main.js file and find the line that says 'var BUCKET_KEY = "YOUR BUCKET ID";' and replace the YOUR BUCKET ID with your pasted bucket id. 
Go through this same process for the Access Key line below. 
Make sure when the key is pasted into the code that it still has the quotes remaining. Here is an example: 

var BUCKET_KEY = "D7JKXEFXXGJ9";
var ACCESS_KEY = "TlGImW8S2maMXoqgtfOxvJZ90h82jSOf";

(your numbers will be different)

Remember to save once you update the code!

##Step 7

Now, let's get in the right view on Initial State to view your data as we capture it real time. 
Click on the new bucket you created. 
Then, click on the waves view.
(Note, Initial State may prompt you to go through some tutorials. I would walk through these as they will help you understand the interface)

##Step 8

Going back to Kinoma Studio, 



##Stop collecting data by pressing 'Stop' in Kinoma Studio. 

Now, in Initial State, we can 





