### Jenkins-demo

 Jenkins application starts on port 8080
 
 Two ways to install and run Jenkins: 
  - install the Jenkins app on the OS directly
  - run Jenkins image and start Jenkins as a docker container

 --> Open port 50000 on Jenkins: here Jenkins master and worker nodes communicate
 --> Jenkins can be built and started as a cluster if you have large workloads that you are running with Jenkins
 --> Initial Jenkins password is located at: 

  - spin up an EC2 instance on AWS
  - open port 22 (for ssh) and port 8080(access jenkins externally) in inbound rules for the security group attached
  - we will run Jenkins's official image to start Jenkins on the Ubuntu server
    
  - For this, we need the installation of docker on the server
  - sudo apt update
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
 
  - setup password by giving the initial password stored at the location mentioned in UI
    ![image](https://github.com/hemu07/Jenkins-demo/assets/90203539/2a01d301-82c4-49dd-b20a-0c23406ebbe5)
    
  - install the plugins manually or automatically
    ![image](https://github.com/hemu07/Jenkins-demo/assets/90203539/7c494c78-53a2-444d-9afd-b90dafaa2a7a)

  - setup the first admin user
  - Jenkins is up and running
    ![image](https://github.com/hemu07/Jenkins-demo/assets/90203539/6bcd11bb-0f97-447e-8b58-18f869107b8e)

  - we can manage and configure build tools and package managers from the Tools tab under the manage Jenkins option:
    ![image](https://github.com/hemu07/Jenkins-demo/assets/90203539/9aae14da-4fec-467d-b77e-fde955562dc1)

