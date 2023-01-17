pipeline{
    agent any
    stages{
        stage("sonar quality check"){
            agent{
                docker {
                    image 'adoptopenjdk/openjdk11:ubi'
                }
            } 
            steps{
                script{
                    withSonarQubeEnv(credentialsId: 'token-sonar') {
                       
                      sh 'chmod +x gradlew'
                      sh './gradlew sonarqube'
                    
                    }  
               }          
           }
       }
   }
}