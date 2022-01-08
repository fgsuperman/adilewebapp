pipeline {
     agent { docker { image 'maven:3.8.4-jdk-11'  } }
           
     
    stages {
        stage('Build') {
            steps {
                echo 'Building stage'
                sh 'mvn --version'
                sh 'mvn clean package'
                
            }
        }
        stage('Generate docker image') { 
            steps {
                echo 'Generating docker image'
                sh 'docker build -t adilewebapp:v1.0 .'
                
            }
            post {
                always {
                    echo 'post steps'
                }
            }
        }
    }
}
