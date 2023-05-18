# KRAMA KATA (Local Language Translator)
   
 [![Platform](https://img.shields.io/badge/platform-Android-green.svg)](http://developer.android.com/index.html)

### What is Krama Kata?

KRAMA KATA is an application that provides information as a translator of various regional languages that uses natural language processing technology and artificial intelligence to translate text from one language to another. It is hoped that this application can help Indonesian people to get to know each other and learn regional languages in Indonesia. 

## Table of Contents

- [Installation](#installation)
- [Demo](#Demo)

### Installation 
Clone this repository by using this one  
```
    https://github.com/hilmycool/KramaKata.git
```    

## Demo

# Mobile Programming Android
### Technology Used
### UI
- [Material Design](https://material.io/develop/android)
- [Glide](https://github.com/bumptech/glide)
- [Recycler View](https://github.com/codepath/android_guides/wiki/Using-the-RecyclerView)

### Database
- [Cloud Firestore](https://firebase.google.com/docs/firestore)


# Machine Learning

============================================================================================================================================

# Cloud Computing 
## Create Databases for Frontend 

![Database Architecture](https://user-images.githubusercontent.com/82069840/121268889-044ca880-c8e9-11eb-8721-70dfe30ed044.png)

In this section, we use Cloud Storage to store sign language image and gif data 
for Frontend purposes in the IndoSign application.
And after all data is stored in cloud storage and set permissions for all users to be 
viewer, we use Cloud Firestore to create database and connect it to Firebase so Android 
Team can easily access its data in database.

### Step 1 : Create Bucket and Upload Folder/File on Cloud Storage
In the Google Cloud Platform menu navigation, select Cloud Storage and then create a new bucket. After
the bucket is created in the permissions section add members and type all users then select
role Cloud Storage -> Storage Object Viewer, it is done so that the data can be accessed by the public.
After that, upload a file/folder containing sign language images and gifs into the selected bucket
already made.

### Step 2 : Create Databases on Firestore
Create a new database in Firestore then connect to the connected firebase
with projects on Google Cloud Platform.
- Create a collection by writing the collection id according to the data collection that you want
will be entered.
- Add Document and input document id or can select auto id
- Add field and enter field name, field type, and field value. For field value "image"
Enter the public access link for the uploaded image/gif file in Cloud Storage.


## Deploying Machine Learning Model on Google Cloud Function

![Deploy ML Architecture](https://user-images.githubusercontent.com/82069840/121268937-19293c00-c8e9-11eb-9dc0-d72abf5bab69.png)

Machine Learning models from Tensorflow are added to buckets that have been 
created in Cloud Storage. Then run the python script that has been created by 
the Machine Learning team in the cloud function to handle requests and download models 
from Cloud Storage. Next, test the model in Cloud Function and return the prediction 
results to the user in the form of a response. and lastly make a request in the Cloud 
Function using the URL from the triggers tab.

### Step 1: Create Bucket and Upload Model from Tensorflow
After the model has been prepared by the Machine Learning team at Tensorflow, the model is uploaded to
Cloud Storage. In the Google Cloud Platform menu navigation, select Cloud Storage and then create
a new bucket. After the bucket is created, upload the model into the bucket you just created.

### Step 2: Create Cloud Function for Deploy Machine Learning Model
- Create Cloud Function and use python 3, then select the http trigger
- Enter the python script to handle requests and to download models from Cloud Storage.
for code is in [main.py](https://github.com/khairul3/BISINDO-Sign-Language-Recognition/blob/master/cloud/main.py) and [requirements.txt](https://github.com/khairul3/BISINDO-Sign-Language-Recognition/blob/master/cloud/requirements.txt) .
- Perform model tests in the cloud function
- Improved prediction results to the user in the form of a response
- Use the url from the trigger tab in the Cloud Function to make a request to the Cloud Function.

===============================================================================
