# Dockerfile for building a MongoDB service

# Pull base image.
    # FROM line specifies that this image is based on antother image 
    # (in this case mongo, which has MongoDB installed)
FROM mongo

# create user,  and let this new user be the owner of the dir
RUN useradd treehouse  

# create working dir
WORKDIR /data

# change owner of dir from root to new user
RUN chown treehouse /data
    # chown stands oor change ownership

# change the user of the container from root to new user
USER treehouse

# commands to create a file wiith the username
    # since the USER is not root, this line will create an error:permision denied if the chown are not set
RUN whoami > user.txt

# Define mountable directories.
VOLUME ["/data/db"]

# Define default command.
    # CMD line specifies a command that will be run when the container starts
    # (in this case MongoDB service)
CMD ["mongod"]

# Expose ports.
    # EXPOSE lines expose network ports within the container to the host operating system, 
    # so that other apps can make network connections to the apps running inside the container.
    #   - 27017: process
    #   - 28017: http
EXPOSE 27017
EXPOSE 28017


# 1.  | building an image |

#   build subcommand to build the image
#   -t flag to tag the image we want to build
#   . to run the current directory
#   laslty name your image
#?       $ docker build -t mongotest .


# 2.  | creating a container |

#   -p flag (publish) to publish the ports that are exposed in the image
#   port number we want to publish : port number that is exposed
#   lastly provide the name of the image you want to base your container on
#?       $ docker run -p 27017:27017 -p 28017:28017 mongotest
#   or 
#?       $ docker run -p 27017:27017 --detach mongotest
#   --detach wil run the container in the background


# 3.  | accessing the container shell | 

# If you want to access the shell of a container after running the:
# docker run -p 27017:27017 -p 28017:28017 mongotest
# You have to expose the shell in the container, if you are running docker >= 1.3
#   container id or name can be found with:
#?       $ docker ps
#           ps stands for process status
# You need you to type in your host OS:
#?       $ docker exec -it [IDofContainerOrName] bash` 
#           -i = for interactive an session
#           t = for teletype interface, so you can communicate with the shell using your terminal
    #! niet gebruikelijk om je container's terminal te gebruiken

