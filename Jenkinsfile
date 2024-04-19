@Library('shared-library') _

pipeline {

environment { 
        imageName = 'algn48/nti-app'
    }

    agent any
    stages {
        stage('Build and Push Docker Image') {
            steps {
                
                oldDockerBuildAndPush(image: "${imageName}", DockerhubCredentials: 'DOCKERHUB')
            }
        }
    }
}