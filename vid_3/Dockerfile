# Base Image
    # You start a Dockerfile with FROM
    # tag is optional
FROM ubuntu:latest

# Commands to run to install dependencies
RUN apt-get update -y  #? Shell form
RUN ["apt-get", "update", "-y"]  #? exec form --> prefered

RUN apt-get install -y python3

# When you pass commands to the container, what should interpret them
ENTRYPOINT ["python3"]

# Command to run when the container starts
    # only one command instruction per Dockerfile
CMD ["app.py"]


# Copy apps from the local folder to the Docker container
    # the last name listed is the name it wil have in the container
COPY app.py app.py
COPY alternate.py alternate.py

# Adds can do everything that copy can, plus it can download files from a URL or decompress files form tar archives
    # use COPY unless you want the extra functionalities, since ADD can behave in surrising ways
#! ADD http://google.com/robot.txt robot.txt

# Make port available
EXPOSE 8080