@Library('shared-library') _

pipeline {
    agent any
    stages {
        stage('Build and Push Docker Image') {
            steps {
                
                oldDockerBuildAndPush(imageName: 'algn48/nti-app', DockerhubCredentials: 'DOCKERHUB')
            }
        }
    }
}