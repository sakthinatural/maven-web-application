


pipeline {
    agent any


    stages {
        stage('checkout code') {
            steps {
                git 'https://github.com/sakthinatural/maven-web-application.git'
            }
        }
		stage(" Maven Clean Package"){
            def mavenHome =  tool name: "Maven-3.5.6", type: "maven"
            def mavenCMD = "${mavenHome}/bin/mvn"
            sh "${mavenCMD} clean package"
            
            } 
    }
}
