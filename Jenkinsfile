pipeline{
agent any
        tools{
        maven 'MAVEN 3.6.3'
        jdk 'jdk1.8.0_241'
        }
        stages{
                stage('build'){
                               steps{
                               bat 'mvn compiler:compile'
                               }
                               post {
                        success {
                        bat "echo 'Projet lors de la compilation du projet'"
                        
                        }
                               
                               }
                
                }
                stage('Test'){
                              steps{
                              bat 'mvn test' 
                              }
                              post {
                                    
                                    junit '**/target/surefile-reports/*.xml'                                             
                              
                              }
                              
                }
                stage('couverture'){
                                    steps{
                                    bat 'mvn cobertura:cobertura -Dcobertura.report.format=xml'
                                    
                                    }
                                    post {
                                    always{
                                    cobertura coberturaReportFile: '**/target/site/cobertura/coverage.xml'
                                    }
                                    }
                
                }
        
        }





}
