
pipeline {
    agent any
	
	tools{
	maven 'maven3.8.3'
}


    stages {
        stage('checkout code') {
            steps {
                git 'https://github.com/sakthinatural/maven-web-application.git'
            }
        }
		stage('build') {
            steps {
               sh "${maven}/bin/mvn clean package"
            }
        }
    }
}
