


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

        stage(" Sonar Analysis"){
            environment {
                SONAR_URL = "http://18.234.169.191:9000"
            }

            steps{
                withCredentials([string(credentialsId: '09b7aaa6-4b6c-4899-8455-6977ee1a5a93', variable: 'sonar', variable: 'SONAR_AUTH_TOKEN')]) {
    sh "mvn sonar:sonar"
}
            }

            

            






    }
}
