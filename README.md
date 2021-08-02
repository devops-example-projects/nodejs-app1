# nodejs-app-mss

To start this application first you can get this repo code using below url

git clone https://github.com/MithunTechnologiesDevOps/nodejs-app-mss.git

cd nodejs-app-mss
npm install

node app.js 

(OR) 

npm start

To Execute the SonarQube Repor, execute the below command.
npm run sonar

(OR) 

node sonar-project.js

# Jenkins Scripted Pipeline 
node
{
	stage("CheckOut")
	{
		git branch: 'main', url: 'https://github.com/devops-example-projects/nodejs-app1.git'	
	}
	stage("Build")
	{
		nodejs(nodeJSInstallationName: 'NodeJS 15.3.0')
		{
			sh "npm install"
		}
	}
	stage("Run")
	{
		nodejs(nodeJSInstallationName: 'NodeJS 15.3.0')
		{
			sh "npm start"
		}
	}
}
