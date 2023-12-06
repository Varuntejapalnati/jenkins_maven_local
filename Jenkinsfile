pipeline {
    agent any 
    stages {
        stage('Compile and Clean dev') { 
            steps {

                bat "mvn clean compile"
            }
        }
        stage('Test the dev') { 
            steps {
                bat "mvn test site"
            }
            
             post {
                always {
                    junit allowEmptyResults: true, testResults: 'target/surefire-reports/*.xml'   
                }
            }     
        }

        stage('deploy dev') { 
            steps {
                bat "mvn package"
            }
        }

    }
}
