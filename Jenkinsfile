


pipeline {
    agent any
	
	 agent {
    docker {
      image 'abhishekf5/maven-abhishek-docker-agent:v1'
      args '--user root -v /var/run/docker.sock:/var/run/docker.sock' // mount Docker socket to access the host's Docker daemon
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
