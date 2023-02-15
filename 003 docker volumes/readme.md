You can find the tutorial for Docker Volume at this link 

https://youtu.be/VOK06Q4QqvE

The commands are : 

docker volume create volumeName

docker volume ls

docker volume inspect volumeName

Screenshot of Terminal 

[![image.png](https://i.postimg.cc/FzpVg4B2/image.png)](https://postimg.cc/QKB7hRsb)

We are doing this test example on a Jenkins container :

#### Commands : 

docker pull jenkins/jenkins

docker run --name myjenkins -p 8080:8080 -p 50000:50000 -v TestVolume:/var/jenkins_home -d jenkins/jenkins

##### instead of mounting to a volume we can also mount a physical location on our harddrive

in the above command I am naming my container as myjenkins and exposing the ports on host at 8080 and 50000 , and attaching /var/jenkins_home folder inside jenkins container to my TestVolume outside container so that I can acces it even when container is deleted

I am running the container in detached mode

[![image.png](https://i.postimg.cc/HscvQJ2m/image.png)](https://postimg.cc/F7vxvH8C)

Jenkins opened : 

[![image.png](https://i.postimg.cc/ncT7hxgD/image.png)](https://postimg.cc/0bMrVT8k)

#### Entering integrated terminal of jenkins by this command : 

docker exec -it myjenkins /bin/bash

[![image.png](https://i.postimg.cc/QxS4GRq6/image.png)](https://postimg.cc/bsDH1VWb)

Jenkins password entry by entering into integrated terminal of jenkins and revealing the password : 


[![image.png](https://i.postimg.cc/XNkBs3Vz/image.png)](https://postimg.cc/bddvv7Sx)

#### Here you can see that the myjenkins container is using TestVolume

[![image.png](https://i.postimg.cc/CKMwLTyz/image.png)](https://postimg.cc/75RFmRZk)

#### Here I am accesing Jenkins from myjenkins container

[![image.png](https://i.postimg.cc/kXPwFtct/image.png)](https://postimg.cc/c6TQdCPs)

#### Now I have create one more instance of Jenkins container names myjenkins1

[![image.png](https://i.postimg.cc/C5gDDbgh/image.png)](https://postimg.cc/hz2fRzv6)

[![image.png](https://i.postimg.cc/ZRh0DZDj/image.png)](https://postimg.cc/KKJZ1Xbg)

In the image above you can see that the new instance is running at 8001 port and we are directly getting login option now I'll login using the user-name and password which I created in myjenkins instance

[![image.png](https://i.postimg.cc/kMTXWx9T/image.png)](https://postimg.cc/14NQQV8F)

(In the image above you can see that the job we create in myjenkins container is also visible in myjenkins1 container)

#### Now I will delete first instance

(Command to stop myjenkins instance and remove from memory)
[![image.png](https://i.postimg.cc/Zn2GVYw5/image.png)](https://postimg.cc/8fdXCG82)


[![image.png](https://i.postimg.cc/fRmNqXnn/image.png)](https://postimg.cc/68Wgy8pY)

(This Screenshot shows that first instance is not available )

BUT....still, data is accesible from 2nd instance

[![image.png](https://i.postimg.cc/cH52L4yB/image.png)](https://postimg.cc/KkBJ9bY1)
