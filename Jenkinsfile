@Library('shared-library') _

pipeline {

environment { 
        imageName = 'algn48/nti-app-python'
        kubernetscerdential    = 'KUBERNETES'
        yamlfiles = 'kuberenetes/DeploymentAndServices.yml'
        
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
                    buildPushtoHub([ image: "${imageName}:${BUILD_NUMBER}", DockerCredentials: 'DOCKERHUB' ])
                } 
            }
        }
    
    
    
    stage('Deploy in kubernetes') {
            steps {                                     

                    sh "sed -i 's|image:.*|image: ${imageName}:${BUILD_NUMBER} |g' ${yamlfiles} > ${BUILD_NUMBER}:${yamlfiles}"
                    Deploykubenetes(pathofyamlfile: "${BUILD_NUMBER}:${yamlfiles}", k8scerdential: "${kubernetscerdential}")
            }
        }
    
    
    
    
    
    
    
    }
}
