pipeline{
    agent any  
    stages{
        stage("maven build"){
           steps{
            sh "mvn clean package"
             archiveArtifacts artifacts: "**/*.jar"
            } 
        }
            
        stage("sonarbuild"){
            steps{
                script {
                     withSonarQubeEnv(credentialsId: 'sonarganesh') {
                         sh "mvn sonar:sonar"
                         }
                }
            }
        }
    }
}