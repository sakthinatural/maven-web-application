


pipeline {
    agent any
    tools { 
        maven 'maven3.9.5' 
    }


    stages {
        stage('checkout code') {
            steps {
                git 'https://github.com/sakthinatural/maven-web-application.git'
            }
        }

        
		stage(" Maven Clean Package"){

            steps{
                sh "mvn clean package"
            }
            
            
            } 
    }
}
