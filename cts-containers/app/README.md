docker build -t jpalaparthi/ctsapp:v0.1 .

1- Create Dockerfile
2- Build Docker Image
3- Push image to registry 
    3.1. Image is pushed to Docker
    3.2 To push other than Docker Hub -> acr, ecr,gcr or quey,jfrog

Install azure cli on your machine

1. az login  // this takes you to the azure login through the browser
2. az acr login --name ctsapp
3. Already a image has been built using docker build
4. Re tag the image with acr details
    if you dont have your image 
    // docker.io/jpalaparthi/demoapp1
    // ctsapp.azurecr.io
    // docker.io/jpalaparthi
    docker pull jpalaparthi/ctsapp:v0.1 // This is alaredy there in docker hub, I pushed it
    // if you have your own image, replae jpalaparthi/ctsapp:v0.1 with your image
    docker tag jpalaparthi/ctsapp:v0.1 ctsapp.azurecr.io/ctsapp:v0.1
5. docker push ctsapp.azurecr.io/demoapp1:v0.1