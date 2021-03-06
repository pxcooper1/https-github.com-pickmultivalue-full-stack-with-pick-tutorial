[![Getting jBASE Docker running and create demo data](video-thumb.jpg)](https://youtu.be/gkHoVHq4J2c)
  
# How to Set Up Demo Data in jBASE
In this tutorial we're will use show you how to install the docker application, download the latest jBASE Container and get it up and running on your system. Lastly we will create a demo account and demo table and populate with data.

1. [Sign Up for a free Docker account](#signup-for-free-docker-account)
1. [Download and Install Docker](#download-docker-application)
1. [Download jbase container](#download-the-jbase-container-and-get-it-running)
1. [Create account DEMO and file containing basic program](#creat-demo-account-in-jbase-and-create-file-to-contain-the-basic-program)
1. [Install make demo program](#get-basic-program-source-that-will-create-and-populate-the-demo-file)
1. [Upload program source to jBASE](#upload-program-source-code)
1. [Run make demo program and create demo file](#run-program-to-create-demo-file)

## Signup for free Docker account
You will need to do is go to [Docker.com](https://www.docker.com) and register for a free account.  To register you click on the [get started button](https://www.docker.com/get-started) at the top right. Scroll down to [choose a plan](https://www.docker.com/pricing). Then click on the Signup for Free. After you register you will get an email that you will use to verify your account.

## Download Docker Application
Now to download and install the docker application again go to [Docker.com](https://www.docker.com) and click on the [get started button](https://www.docker.com/get-started) at the top right.  Scroll down to the docker desktop on left and download the version for you OS. Run the install once the download is completed. After the install is complete you will need to reboot your computer.

## Download the jBASE container and get it running
Once you have the docker application installed you will need to download the jBASE container. You do this by:
  
1. Open a command prompt window.
1. Type in `docker pull zumasys/jbase_base` and hit enter.  
  This will download the latest jBASE Docker container with jBASE already set up. 
1. Start the docker by typing in the following command from your command window `docker run -it -p 20002:20002 zumasys/jbase_base` and hit enter.
  
Now you have jBASE up and running from Docker! 
  
## Creat DEMO account in jBASE and create file to contain the basic program
Now that you are in your jBASE docker you can create a account in jBASE that will store the the demo file. 
  
**Create Account**  
Simply execute the command `CREATE-ACCOUNT DEMO`. Now to logot the demo account simply type in `LOGTO DEMO`. 
  
**Create Basic file**  
We will now create a basic program file to hold the program that will create the demo file.  The command is `CREATE-FILE BP TYPE=UD`. The type of UD will create a directory type file which is the prefered type for basic programs in jBASE.
  
## Get basic program source that will create and populate the demo file
 You are already at the correct page in github that contains the source code.  The *make demo program* source code can be found by following [full-stack-with-pick-tutorial](https://github.com/pickmultivalue/full-stack-with-pick-tutorial) -> [back-end/jbase](https://github.com/pickmultivalue/full-stack-with-pick-tutorial/tree/master/back-end/jbase) -> [setting-up-jbase-demo-data](https://github.com/pickmultivalue/full-stack-with-pick-tutorial/tree/master/back-end/jbase/setting-up-jbase-demo-data) -> [makedemofile](https://github.com/pickmultivalue/full-stack-with-pick-tutorial/blob/master/back-end/jbase/setting-up-jbase-demo-data/makedemofile). This will bring up the make demo program source code. You will need to higlight the code and copy as we will simply paste the code into the program in jBASE.
  
## Upload program source code
Now we need to upload that source code program to jBASE. 
  
1. Now go back to jBASE (command prompt window).
1. To edit the program type in `JED BP MAKE.DEMO`. 
1. Simply paste the program from the prior step in. 
1. In jBASE to create an executable program you need to compile and catalog the program. We will File the program, compile and catalog in one step by hitting the escape key and typing `FIBC`. 
  
## Run program to create demo file  
Now we are ready to create the demo file by running the program!
  
1. Type the command `RUN BP MAKE.DEMO`. 
1. The program will ask two questions: 
   1. First the number of records you want to create. We'll create 100. 
   1. Second the file name. Please use *DEMO.FILE* for the filename as that is what will be used in future videos.  
    
The program randomly generates the data for the a static list of each data element. Lastly we list the file to see that the file was created and populated the command is `LIST DEMO.FILE FIRSTNAME LASTNAME ADDR1`.
