Project Details:

Continuous Integration/Delivery Pipeline: Set up a CI/CD pipeline using popular tools like Jenkins and integrate it with guthub CI ....etc.
Configure the pipeline to automatically build, test, and deploy applications whenever changes are made to the code repository.
 Focus on integrating different stages of the pipeline, such as code linting, testing, and deployment, without writing code.


 Project No. 1
 ___
the details of the CI/CD Pipeline project using Jenkins, orGitlab CI .... etc:

1. Install Jenkins: Set up Jenkins on your server and ensure it is running successfully.
	- Install Java-OpenJdk : sudo yum install -y java-11-openjdk
	- Install the Repo and Key, and Then Install Jenkins
 	1 - Install wget:  sudo yum install -y wget
 	2 - Download the repo:  sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
 	3 - Import Jenkins Key: sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key
 	4 - Install Jenkins: sudo yum install -y jenkins 
 	5 - Enable Jenkins: sudo systemctl enable jenkins
 	6 - Start Jenkins:  sudo systemctl start jenkins
 	7 - Install Git : sudo yum install git -y 
 	8 - in new tab accesst your ip following with:8080 then
 	9 - go to the path in the login screen to get the administrator password: 
    			  sudo cat /var/lib/jenkins/secrets/initialAdminPassword
 	10- the hash password and next to installing the plugins 
 	11- create a new user and finaly jenkins is installed.


2. Project Setup: Create a new project in Jenkins and choose the appropriate project type, such as Freestyle or Pipeline.
----
1- Create a new project : Click on a New item on the left
2- Enter the name of project and select type : pipeline
3- write description of your project then save


3. Connect Code Repository: Link your code repository (e.g., Git) with Jenkins. Configure Jenkins to listen for any changes in the repository and trigger project builds.
------
1- from Github open profile settings > Developer Settings > Personal Access tokens classic > Generate new token (classic) and 
   select these scopes  : admin:repo_hook  then Generate Token , Copy Token ID  :    

2- Manage Jenkins > System > scroll down a bit to the GitHub section > Add GitHub Server > select GitHub Server Give this a Name of github > Click the Add dropdown
   select Jenkins > Kind > select Secret text > paste the token we copied earlier to Secret > ID of github_key, and a Description of GitHub Key. > Add > Back on the Configure System 
   > select that GitHub Key we just created, from the Credentials dropdown. > click Test connection > Save.

4. Configure Build Stage: In this stage, configure the necessary build actions to compile your application. This may involve executing commands like installing dependencies and running the build script.

5. Test Stage: In this stage, define the required quality checks for your application. You can use tools like Maven JUnit for unit testing or other tools for automated testing.

6. Deployment Stage: In this stage, configure the automatic deployment of your application after passing the testing stage. You can use tools like Shell Scripts or Docker to deploy the application to the target server or environment.

7. Configure Notifications: Set up notification settings to notify the development team about the project's status, whether it is successful or has failed. You can send notifications via email or instant messaging applications.

By following these steps, you'll have a basic CI/CD pipeline set up using Jenkins. As you gain more experience, you can explore advanced configurations, such as environment-specific deployments, parallel testing, and integration with additional tools and services.
