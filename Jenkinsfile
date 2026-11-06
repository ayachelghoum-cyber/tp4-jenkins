pipeline {
    agent any

    tools {
        maven 'Maven'
    }

    parameters {
        string(name: 'VERSION', defaultValue: '1.0.0', description: 'Version à déployer')
        choice(name: 'ENV', choices: ['dev', 'staging', 'prod'], description: 'Environnement')
        booleanParam(name: 'executeTests', defaultValue: true, description: 'Lancer les tests ?')
    }

    stages {
        stage("Build") {
            steps {
                echo "Building the application..."
                sh 'mvn --version'
            }
        }
        stage("Test") {
            when {
                expression { params.executeTests == true }
            }
            steps {
                echo "Testing the application..."
            }
        }
        stage("Deploy") {
            steps {
                echo "Deploying version ${params.VERSION} sur ${params.ENV}"
            }
        }
    }
}
