pipeline{
    agent any
    stages{
        stage("sonar quality check"){
            agent{
                docker {
                    image 'adoptopenjdk/openjdk11:jdk-11.0.9.1_1'
                }
            } 
            steps{
                script{
                    withSonarQubeEnv(credentialsId: 'sonar-token') {
                       
                      sh 'chmod +x gradlew'
                      sh './gradlew sonarqube'
                    
                    }  
               }          
           }
       }
   }
}