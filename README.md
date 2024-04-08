### Jenkins-demo

 Jenkins starts on port 8080 by default
 
 > Two ways to install and run Jenkins: 
  - install the Jenkins app on the OS directly
  - run Jenkins image and start Jenkins as a docker container

 --> Open port 50000 on Jenkins: here Jenkins master and worker nodes communicate
 --> Jenkins can be built and started as a cluster if you have large workloads that you are running with Jenkins
 --> Initial Jenkins password is located at: /var/volume_name/secrets/initialadminpassword

  - spin up an EC2 instance on AWS
  - open port 22 (for ssh) and port 8080(access jenkins externally) in inbound rules for the security group attached
  - we will run Jenkins's official image to start Jenkins on the Ubuntu server
    
  - For this, we need the installation of docker on the server
  - `sudo apt update`
  - sudo apt install docker.io
    ![image](https://github.com/hemu07/Jenkins-demo/assets/90203539/99c93d15-0b45-4d36-bcda-8886b79e6c9d)
    
  - By default, the Docker daemon socket is only accessible to users in the "docker" group. You can add your current user to this group using the following command:
  - sudo usermod -aG docker $USER
  - docker login
  - enter username & password or PAT to login
    ![image](https://github.com/hemu07/Jenkins-demo/assets/90203539/33abb65a-099e-426e-bd57-c91978f45ca5)
    
  - Starting Jenkins on the server
    ![image](https://github.com/hemu07/Jenkins-demo/assets/90203539/735ff21e-a5b3-4e5b-a945-bd80a52d8062)
    ![image](https://github.com/hemu07/Jenkins-demo/assets/90203539/fa3361bd-1647-4913-9292-ecc2ed9122cf)

  - Access Jenkins UI from the browser
    ![image](https://github.com/hemu07/Jenkins-demo/assets/90203539/8446bafc-b637-489e-ae95-2dcbe9f5cf15)
 
  - setup password by giving the initial password stored at the location mentioned in the UI
    ![image](https://github.com/hemu07/Jenkins-demo/assets/90203539/2a01d301-82c4-49dd-b20a-0c23406ebbe5)

  - when we log in to the Jenkins container --> we are logged in as a Jenkins user instead of a root user as by default Jenkins is started as a Jenkins user (security best practice)
    
  - install the plugins manually or automatically
    ![image](https://github.com/hemu07/Jenkins-demo/assets/90203539/7c494c78-53a2-444d-9afd-b90dafaa2a7a)

  - setup the first admin user
  - Jenkins is up and running
    ![image](https://github.com/hemu07/Jenkins-demo/assets/90203539/6bcd11bb-0f97-447e-8b58-18f869107b8e)

  - inspect the Jenkins mount volume location
    ![image](https://github.com/hemu07/Jenkins-demo/assets/90203539/9facf09a-3f89-4880-a523-3740193725a3)

  - we can manage and configure build tools and package managers from the Tools tab under the manage Jenkins option:
    ![image](https://github.com/hemu07/Jenkins-demo/assets/90203539/9aae14da-4fec-467d-b77e-fde955562dc1)

  - To log in as a root user to the Jenkins container, use -u flag :
    ![image](https://github.com/hemu07/Jenkins-demo/assets/90203539/78d77032-b35c-408d-a321-333c588aff00)
    
  - installing nodejs and NPM in the container, we logged in as root user
  - checking the Linux distro container is using
    ![image](https://github.com/hemu07/Jenkins-demo/assets/90203539/bf7a7682-e13e-48d8-825b-92fc53ac28fc)

  - download node: https://deb.nodesource.com/
    ![image](https://github.com/hemu07/Jenkins-demo/assets/90203539/6354baa0-a8d5-47ea-aaba-c237c9c89dda)

    apt-get install -y nodejs
    ![image](https://github.com/hemu07/Jenkins-demo/assets/90203539/b81d645d-59c5-405f-a1ff-14316aecc078)

  - Creating a job:
     - under new item -> create a job or directly from the UI itself
     - freestyle for demo purposes/ small projects, learning Jenkins etc
     - for the Production environment, we will be using pipeline and multipipeline jobs
     - on clicking the build now button, the job gets run
       ![image](https://github.com/hemu07/Jenkins-demo/assets/90203539/cff0e8b0-d9ce-49d5-a646-96fdaba0fad4)
     - we can see the console output on clicking that tab
       ![image](https://github.com/hemu07/Jenkins-demo/assets/90203539/b8f3dd28-9cbc-437d-8519-74173c4ad79c)
     - integrate with the GitHub account to start the build process as soon as changes are committed to the repo
       ![image](https://github.com/hemu07/Jenkins-demo/assets/90203539/e85cd60c-9dd0-43db-91ce-980d38d8321a)
     - the build now takes longer than the previous one because of this integration
       ![image](https://github.com/hemu07/Jenkins-demo/assets/90203539/64282678-557c-4d01-b929-64dceabd0f69)
       ![image](https://github.com/hemu07/Jenkins-demo/assets/90203539/79e8bcdf-e948-4a1b-af37-aa5970727bb0)

     - added new branch "jenkins-job", created test.sh script to print npm version
       ![image](https://github.com/hemu07/Jenkins-demo/assets/90203539/aced8685-535b-462b-b226-26ebedfbeb40)

     - build this branch in Jenkins
       ![image](https://github.com/hemu07/Jenkins-demo/assets/90203539/dd95a084-565c-4d74-9cd8-17f0419342a5)
     - in the shell command give execute permission to Jenkins user to run test.sh
       ![image](https://github.com/hemu07/Jenkins-demo/assets/90203539/b74b13f3-0065-4593-b4bf-0cf6c8ffc645)
     - run the build
       ![image](https://github.com/hemu07/Jenkins-demo/assets/90203539/1e1760a1-7dfe-4506-9b02-e9013b714c64)


    

