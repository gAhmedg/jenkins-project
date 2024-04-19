pipeline {
    agent any

    stages {    

  
          stage('dockerBuildAndPush')
          {
            steps {
                script {
                    oldDockerBuildAndPush.call (imageName: "algn48/new-app-nti" )

                }

            	 
                   }

          }
}   
}

