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
        withCredentials([string(credentialsId: 'sonartoken', variable: 'SONAR_AUTH_TOKEN')]) {
          sh 'mvn sonar:sonar -Dsonar.login=$SONAR_AUTH_TOKEN -Dsonar.host.url=${SONAR_URL}'
        }
      }
    }


    stage("Quality Gate"){
          timeout(time: 1, unit: 'HOURS') {
              def qg = waitForQualityGate()
              if (qg.status != 'OK') {
                  error "Pipeline aborted due to quality gate failure: ${qg.status}"
              }
              else
              {
                error "Pipeline ran successfully: ${qg.status}"
              }
          }
      }



  
  }
}