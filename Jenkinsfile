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
                sh "mvn clean package"
            }
        }
        
         stage("Test Cases"){
            steps{
                sh "mvn test"
            }
        }
    
         stage("docker Cases"){
            steps{
                
             
              sh "docker build -t image1 ."
              
                 
               
               }
            }
        
       
        
        
    }
}
        
