@Library('shared-library') _

pipeline {

environment { 
        imageName = 'algn48/nti-app'
        kubernetscerdential    = 'KUBERNETES'
        yamlfiles = 'kuberenetes/DeploymentAndServices.yml'
        docker-credentials    = 'DOCKERHUB'
    }

    agent any

     stages {
            stage('Verify Branch') {
            steps {
                echo "$GIT_BRANCH"
            }
        
            }
   
        stage('Build and Push Docker Image') {
            steps {
                
               script {
                    test([ image: "${imageName}", DockerCredentials: "${docker-credentials}" ])
                } 
            }
        }
    
    
    
    stage('Deploy in kubernetes') {
            steps {                                     

                
                    Deploykubenetes(pathofyamlfile: "${yamlfiles}", k8scerdential: "${kubernetscerdential}")
            }
        }
    
    
    
    
    
    
    
    }
}
