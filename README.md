# IRS MuleSoft Docker Lab
> MuleSoft lab infrastructure for training Infinite folks

This deploys a simple "Hello World" application to MuleSoft CloudHub using Jenkins Blue Ocean pipeline. It requires an active [AnyPoint Platform](https://anypoint.mulesoft.com) account. of docker containers to create the infrastructure required to support Infinite Resource Solutions' MuleSoft training labs. What is docker? See [Learning](#learning) at the end of this document.



### REQUIREMENTS
* [AnyPoint Platform](https://anypoint.mulesoft.com/login/signup) Trial Account
* [Docker Desktop](https://docs.docker.com/docker-for-windows/install/)

### USAGE
Once you have installed Docker Desktop and created a trial account with AnyPoint Platform, you can launch your Jenkins pipeline by following the steps below:

1. Open your favorite terminal emulator and run the commands below:
```BASH
docker run -p 8080:8080 --name jenkins_blue -d jenkinsci/blueocean
```

2. The jenkins security token required to authenticate to the web interface for the first time will be dynamically generated during the container boot and displayed in the logs. Enter the command below to view the container logs:
```BASH
docker container logs jenkins_blue
```
The output looks something like this:
```
*************************************************************

Jenkins initial setup is required. A security token is required to proceed.
Please use the following security token to proceed to installation:

41d2b60b0e4cb5bf2025d33b21cb

*************************************************************
```
Copy that value to your clipboard.

3. Navigate to http://localhost:8080 and enter the security token you retrieved from the container logs in step #2.

4. Complete Jenkins installation and configuration (COMING SOON!)