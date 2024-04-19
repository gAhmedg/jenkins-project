@Library("Shared-library") _

pipeline {
    agent any

   
environment {
    IMAGE      = 'algn48/new-app-nti' 
}
  
    stages {    


// stage1 
        stage('Verify Branch') {
            steps {
                echo "$GIT_BRANCH"
            }
           
        }


// stage2
  
          stage('dockerBuildAndPush')
          {
            steps {
            dockerBuildAndPush( imageName: "${IMAGE}")
                  }
            
          }

        
   }
} 


