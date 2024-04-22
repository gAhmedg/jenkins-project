//@Library('shared-library') _

pipeline {

environment { 
        imageName = 'algsn48/nti-app'
    }

    agent any

     stages {
        //    stage('Verify Branch') {
        //     steps {
        //         echo "$GIT_BRANCH"
        //     }
        

   
        // stage('Build and Push Docker Image') {
        //     steps {
                
        //         oldDockerBuildAndPush(image: "${imageName}", DockerhubCredentials: 'DOCKERHUB')
        //     }
        // }
    
    
    
    stage('Deploy in kubernetes') {
            steps {
                // sh '''
                //     cd kuberenetes/
                //     kubectl apply -f deployment.yml
                //     kubectl  apply -f services.yaml

                // '''

                script {

                    kubernetesDeploy ( configs: 'kuberenetes/deployment.yml', kubeconfigId: 'KUBERNETES' )
                    sh 'kubectl get all'
                }
            }
        }
    
    
    
    
    
    
    
    }
}