# Hand-in: Short report
The URL to the published container on DockerHub: https://hub.docker.com/repository/docker/sunnivasl/dat250/general 
The URL to my GitHub repository for this project: https://github.com/h591296/DAT250_Assignment_1.git 

## Technical problems during installation of the software development environment and solutions
#### Installing Java
During the initial stages of this exercise, I successfully installed Java without encountering any difficulties. To ensure a smooth installation process, I followed these steps:
    sdk install java
    sdk current 
    java --version
    javac --version

#### Code editor selection
I opted to work with Visual Studio Code (VSCode) since it's the code editor I am most familiar with and prefer to use.

#### Installing gradle
The installation of Gradle, our chosen build tool, went smoothly without any issues. I utilized the following commands to install and verify Gradle:
    sdk install gradle
    gradle -v

#### Git
Although I already had Git installed, I verified its installation by running the command: 
    git -v


## Technical problems during the exercise of making an application production-ready and solutions
#### Step 1: Source code versioning
Initially, I had no problems using GitHub. The repository creation and import into VSCode went smoothly. However, I encountered challenges when attempting to push changes from my local project to the GitHub repository. These challenges stemmed from discrepancies between my local branch and the remote branch due to changes in the readme.md file.

After troubleshooting the issue and failing to find a solution, I decided to resolve it by deleting both the GitHub repository and the local project. On the second attempt, I did not encounter the same challenges, and all commits are reflected from today, Sunday, September 3rd.

#### Step 2: Set up build system
This step proceeded without any significant issues. Initializing Gradle and selecting the appropriate options was straightforward. The following commands were executed successfully:
    ./gradlew check
    ./gradlew build
    ./gradlew run

However, when adding files from my local computer to version control, I encountered some difficulties. The git add command did not work as expected for all files. Eventually, I managed to use variations of this code where I would only add files with specified file extensions (git add *.fileExtension), and not using the file name itself as the code suggests is possible. When working in the terminal, I always made sure thatI remained in the correct directory. It also took some time before I understood what you wanted us to do when you requested that the remaining files should be ignored by adding respective entries to my .gitignore. 

### Step 3: Fix compilation errors
I found the information regarding the required dependency somewhat vague initially but managed to resolve it within a short period. The provided localhost link allowed me to calculate that there are 9.144 meters in 30 feet. However, I spent considerable time trying to eliminate the "Javalin: It looks like you don't have a logger in your project" message. I believe I spent at least three days trying to figure out how to add a logger. I tried adding a xml-file and added multiple lines of code into both the App.Java fil, importing all kinds of things connected to Javalin, and into the build-file. After some research, I discovered that a single line of code specifying the project dependencies was all that was required.

#### Step 4: Quality assurance
This was a pretty easy step, because I only needed to move a part of the main code into a method, which was then called from the main method. On the tests however, I experienced that they would fail multipe times. After discussing with a friend from class, we figured that it had to do with the rounding of the calculation. Once i managed to take care of this, the tests were approved. 


## Software validation
Throughout the software installation process, I verified the correctness of the installation and followed the task instructions meticulously. This ensured that the software was functioning as expected at each stage of development.