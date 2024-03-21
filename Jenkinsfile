pipeline {
    agent any 
    
    tools{
        jdk 'jdk11'
        maven 'maven3'
        
    }
    
    
    
    stages{
         stage("docker Cases"){
            steps{
                script{
              withDockerRegistry(credentialsId: '6d3d33dd-7c90-46e7-918a-4564ef706ec0', toolName: 'docker') {
              sh "docker build -t image1 ."
              }
                 
               
               }
            }
        }
        
        stage("Git Checkout"){
            steps{
                git branch: 'main', changelog: false, poll: false, url: 'https://github.com/elaya1818/project018.git'
            }
        }
        
        stage("Compile"){
            steps{
                sh "mvn clean package"
            }
        }
        
         stage("Test Cases"){
            steps{
                sh "mvn test"
            }
        }
       
        
        
    }
}
        
