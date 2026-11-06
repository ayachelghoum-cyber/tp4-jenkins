pipeline {
    agent any
    tools {
        maven 'Maven'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
                 sh 'mvn --version'
                
            }
        }
        stage('Test') {
        
            steps {
                echo 'Testing the application...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                echo "user = ${SERVER_CREDENTIALS_USR}"
            }
        }
    }
    
}
