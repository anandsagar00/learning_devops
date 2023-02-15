I have bild a dockerfile with the instruction below

from alpine
copy sample /my_own_folder
entrypoint ["echo","The instance is running perfectly.\n"]


this chooses base OS as alpine and copies the content of sample folder from my actual laptop to my_own_folder inside container

the entry point is the command which would be run in the alpine OS' terminal ,

Here I have written an echo command to print "The instance is running perfectly.\n"

This way I can be sure that image has been build perfectly and is running perfectly.

IMP : note the difference between CMD and entry point 

In Docker, both CMD and ENTRYPOINT are used to define the default command to be executed when a Docker container starts, but they have different functionalities and use cases.
ENTRYPOINT is used to specify the command that should be executed when the container starts, while CMD is used to provide default arguments to the entry point. ENTRYPOINT is typically used to define the main executable for the container, while CMD is used to specify arguments that will be passed to the ENTRYPOINT.

In summary, ENTRYPOINT specifies the main command to run, and CMD provides default arguments to the ENTRYPOINT. Together, they define the default behavior of a Docker container.
