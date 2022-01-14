   
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
        stage('sonar') {
            steps{

            script{
                def scannerHome = tool 'sonar-scanner';
                withSonarQubeEnv('sonar-server') {
                sh "${scannerHome}/bin/sonar-scanner -Dsonar.projectKey=ejemplo-maven -Dsonar.java.binaries=build -Dsonar.sources=src"
                }
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
