


pipeline {
    agent any
    tools { 
        maven 'Maven 3.3.9' 
        jdk 'jdk8' 
    }


    stages {
        stage('checkout code') {
            steps {
                git 'https://github.com/sakthinatural/maven-web-application.git'
            }
        }

        
		stage(" Maven Clean Package"){
            sh "mvn clean package"
            
            } 
    }
}
