I have tried to make a multi container application using docker compose

This is a bare minimum file , we would also need several other things as well such as attaching a volume,
exposing ports etc.

This is a video tutorial of how to write a docker compose file :
https://youtu.be/HUpIoF_conA

#### The standard name is docker-compose.yaml

Here is an example of what do I mean by multi-container applications

[![image.png](https://i.postimg.cc/Y06dQdD4/image.png)](https://postimg.cc/MfG0SmSx)

IMP : before running a docker-config file make sure to check validity of docker-compose file by
running the command below (You should be in same dir as that of a compose file) :

docker-compose config

after it does not give any error , run command

docker compose up -d

(-d for detached mode)

[![image.png](https://i.postimg.cc/qqwRFC1m/image.png)](https://postimg.cc/bSGpDdcb)

The containers are running in BG

[![image.png](https://i.postimg.cc/ZYxxm7gQ/image.png)](https://postimg.cc/xqqzyR9G)

You can also see this in GUI

[![image.png](https://i.postimg.cc/4NT46wxX/image.png)](https://postimg.cc/232fmQWt)

You can also see that on port 9002 the nginx webserver is also running 

[![image.png](https://i.postimg.cc/gc4X2fKf/image.png)](https://postimg.cc/z3bXd26j)

To stop the containers , run 

docker compose down