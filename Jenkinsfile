pipeline {
  agent any
  tools {
    maven 'maven3.9.5'
  }

  stages {
    stage('sharedlibrary'){
      steps{
          helloWorld()
      }
    }
    stage('checkout code') {
      steps {
        git 'https://github.com/sakthinatural/maven-web-application.git'
      }
    }

    stage(" Maven Clean Package") {

      steps {
        sh "mvn clean package"
      }

    }

    
    stage('Static Code Analysis') {
      environment {
        SONAR_URL = "http://18.234.169.191:9000"
      }
      
      steps {
                withSonarQubeEnv('sonarqube'){
                    // If you are using Windows then you should use "bat" step
                    // Since unit testing is out of the scope we skip them
                    sh "mvn sonar:sonar"
                }
            }
    }


     stage ("Quality Gate ") {
            steps {
                timeout(time: 1, unit: 'HOURS') {
                    waitForQualityGate abortPipeline: true
                }
            }
        }


  
  }
}