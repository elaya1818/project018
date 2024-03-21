pipeline {
    agent any 
    
    tools{
        jdk 'jdk11'
        maven 'maven3'
        
    }
    
    
    
    stages{
        
        stage("Git Checkout"){
            steps{
                git branch: 'main', changelog: false, poll: false, url: 'https://github.com/elaya1818/project018.git'
            }
        }
        
        stage("Compile"){
            steps{
                sh "mvn clean compile"
            }
        }
        
         stage("Test Cases"){
            steps{
                sh "mvn test"
            }
        }
        stage("docker Cases"){
            steps{
                script{
               withDockerRegistry(credentialsId: 'd3f6cf5f-17c6-4fac-ba84-d90ea136cf09', toolname: 'docker') {
                  sh "docker build -t image1 ."
               }
               }
            }
        }
        
        
    }
}
        
