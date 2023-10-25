# flask_5_tailwind
This is assignment #5 for HHA 504


### 
Link of flask app: https://fahima-flask-app-video.azurewebsites.net/


### Video of flask app
https://github.com/Lfahima/flask_5_tailwind/assets/140275869/8dfd7ad9-6e0f-4f26-8cd7-5464341b637b

### Image of flask app
<img width="1509" alt="Screenshot 2023-10-25 at 11 15 05 AM" src="https://github.com/Lfahima/flask_5_tailwind/assets/140275869/091ada7e-910e-4261-8b42-6396a140a1ea">

### Image of flask app with video
<img width="1510" alt="Screenshot 2023-10-25 at 11 15 20 AM" src="https://github.com/Lfahima/flask_5_tailwind/assets/140275869/0d527b94-c7f5-4b19-a43c-39b49ffacf1d">

### Image of flask app video confirming assets are being served from the CDN.
<img width="1508" alt="Screenshot 2023-10-25 at 1 35 27 PM" src="https://github.com/Lfahima/flask_5_tailwind/assets/140275869/36d963ca-9e83-4288-941f-f69d4ef0e9ed">


## Your design rationale and principles followed.
For my design rationale I kept height at full and width at full so the video could be responsive to all devices and sizes. 


## Steps for setting up and using the CDN with your Flask app.
### Setting up the CDN:
1. I first created my storage account and container (the container is where I uploaded my video).
2. I then located to Front Door & CDN, which can be found on the left hand side, under Security + Networking.
3. The only thing I changed when setting up the CDN was for "Service Type Select" I selected "Azure CDN"
4. For the "Profile Name" I typed "fahima-flask-cdn" and for "endpoint name I typed "fahima-cdn"
5. I left "pricing tier" at "Standard Microsoft"
6. For "Query string caching behavior" I selected "select ignore query string"
### Using the CDN with my flask app:  
1. I navigated to home first, then clicked on storage accounts.
2. I clicked on the storage account I created -- "fahimastorageaccount"
3. I clicked on Front Door & CDN, which can be found on the left hand side under Security + Networking
4. I clicked on "fahima-cdn.azureedge.net" which was under Host name and the CDN I created.
5. I copied the Endpoint hostname and pasted into another tab.  
6. I navigated to container, which is on the left hand side, under Data Storage.
8. I clicked on my container which is titled fahima-flask-apps.
9. I then clicked on the video I uploaded.
10. I copied the URL and pasted it into another tab, and I was able to see the video.
11. Now, I copied the URL from the video tab, but only copied everything after .net/ and I pasted that into the Endpoint hostname URL after a / (so I had the Endpoint hostname URL, I added a /, and then pasted the URL from the video, but only everything after .net/) (It looked like this --https://fahima-cdn.azureedge.net/fahima-flask-apps/IMG_4921.MOV).
12. That is the URL I used in my video.html file, in the source.

    
## Steps for deploying your Flask app to the chosen cloud platform.
#### I chose to deploy using Azure, since I was already using Azure. 
#### I used Visual Studio Code instead of Cloud Shell for this assignment because my Cloud Shell was not cooperating and I prefer to use Visual Studio Code, it is much more user friendly and I like how everything is organized. 
#### I went back to lecture slides 2, that had all the steps for Azure and GCP deployment. 
### Steps:
1. I first had to connect my VSC to my Azure acount, so I copied this link: https://fahima-cdn.azureedge.net/fahima-flask-apps/IMG_4921.MOV and hit enter.
2. This link gave me another link that I had to click into, and a code that I had to enter into the the other link provided.
3. I then typed az to make sure my Azure and VSC were connected.
4. I then copied and pasted this code to login: az login --use-device-code  and hit enter.
5. I followed by pasting this code to get the azzure student subscription ID: az account list --output table  and hit enter.
6. I copied the last subscriptionID which was linked to Azure for students and I pasted it into this code: az account set --subscription
yoursubscriptionId (I pasted the ID towards the end where it says yoursubscriptionId)
7. I had already used an old resource group.
8. Finally, I pasted this code: az webapp up --resource-group <groupname> --name <app-name> --runtime <PYTHON:3.9> --sku <B1>
   for groupname I changed it to my resource groupname, which is Fahima504 and for app-name I made up Fahima-flask-app-video.
9. I remembered to remove these symbols <>, because I recall they gave me an error previously.
10. FINALLY, I pasted this code to re-deploy: az webapp up
11. My deployment was succeccful. 

  
## Your observations and benefits of using a CDN and cloud deployment.
My observation and benefits of using a CDN amd cloud deployment was that it was very easy to upload a picture and a video to my flask app and I did not face any errors while doing so. 


## Any challenges encountered and how you addressed them.
The only challenge I encountered was when I tried to upload my video to github, it gave me an errorr stating I was unable to upload since my video was too long. I did some research and had to compress my video so it would fit and be uploaded to github. I used two different websites to compress my videos and it worked. The video was less then 10 mg and I was able to upload to github.  
