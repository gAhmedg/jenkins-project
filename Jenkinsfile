

pipeline {
    agent any

   
environment {
    IMAGE      = 'algn48/new-app-nti' 
}
  
    stages {    


// stage1 
  
          stage('dockerBuildAndPush')
          {
            steps {

    // Log in to DockerHub 
	    withCredentials([usernamePassword(credentialsId: "${DOCKERHUB}", usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
		sh "docker login -u ${USERNAME} -p ${PASSWORD}"
        }
            sh "docker build -t ${IMAGE}:${BUILD_NUMBER} ."
            sh "docker push ${IMAGE}:${BUILD_NUMBER}"	 
            
          }

        
   }
} 


