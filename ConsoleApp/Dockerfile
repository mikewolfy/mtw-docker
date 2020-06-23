# base image
FROM mcr.microsoft.com/dotnet/core/aspnet:3.1

# tells Docker to copy the specified folder 
# on your computer to a folder in the container
COPY bin/Release/netcoreapp3.1/publish/ App/

# changes the current directory inside of the container to App
WORKDIR /App

# tells Docker to configure the container to run as an executable
ENTRYPOINT ["dotnet", "NetCore.Docker.dll"]



# to execute and build the container, run this command
# >>   docker build -t counter-image -f Dockerfile .

# Once complete, run the following command to see the layers
# >>   docker images

# creates a stopped container named 'core-counter' using the 'counter-image' image
# >> docker create --name core-counter counter-image

# then see a list ALL containers
# >>  docker ps -a

# And start, then connect, and then stop the container
# NOTE: --sig-proxy=false ensures that Ctrl+C will not stop the process in the containe
# >>  docker start core-counter
# >>  docker attach --sig-proxy=false core-counter
# >>  docker stop core-counter

# To CREATE AND RUN the image in single command, use 'docker run'
# NOTE, -it  --> run in the current terminal
# NOTE, --rm  --> remove the container once the terminal ends 
# ALSO, you can pass parameters
# >>  docker run -it --rm counter-image 15