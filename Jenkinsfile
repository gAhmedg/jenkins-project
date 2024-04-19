pipeline {
    agent any

   
environment {
    IMAGE_NAME      = 'algn48/new-app-nti' 
}
  // stage1
    stages {    
        stage('Verify Branch') {
            steps {
                echo "$GIT_BRANCH"
            }
           
        }


// stage2
  
          stage('dockerBuildAndPush')
          {
            steps {
            dockerBuildAndPush( imageName: "${IMAGE_NAME}")
                  }
            
          }

        
   }
} 


//###############################################################33
/*pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
*/