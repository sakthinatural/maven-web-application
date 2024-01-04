


pipeline {
    agent any
    tools { 
        maven 'Maven 3.3.9' 
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
