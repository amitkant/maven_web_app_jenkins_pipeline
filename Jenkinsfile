pipeline{
    agent any
    environment {
        PATH = "$PATH:/opt/apache-maven-3.6.3/bin"
    }
    stages{
       stage('GetCode'){
            steps{
				git branch: 'main',
                url: 'https://github.com/amitkant/maven_web_app_jenkins_pipeline.git'
            }
         }        
       stage('Build'){
            steps{
                sh 'mvn clean package'
            }
         }  
	stage('Sonar'){
            steps{
		withSonarEnvironment('Sonarqube')
                sh 'mvn sonar:sonar'
            }
         }  
    }
}
