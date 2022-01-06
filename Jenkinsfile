pipeline {
    agent any
    
    stages{
        stage('Compile'){
            steps{
                script{
                    sh "./mvnw clean compile -e"
                }
                
            }
            
        }
        stage('Test'){
            steps{
                script{
                    
                        sh "./mvnw clean test -e"
                    
                }
                
            }
            
        }
        
        stage('Package'){
            steps{
                script{
                   
                        sh "./mvnw clean package -e"
                    
                }
                
            }
            
        }
        stage('Run'){
            steps{
                script{
                    
                        sh "nohup bash mvnw spring-boot:run &"
                        sh "sleep 30"
                    
                }
                
            }
            
        }
         stage('Testing app'){
            steps{
                sh """curl -X GET 'http://localhost:8081/rest/mscovid/test?msg=testing'"""
                
            }
            
        }
        
    }

}
