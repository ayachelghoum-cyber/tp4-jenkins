def gscript

pipeline {
    agent any

    parameters {
        string(name: 'VERSION', defaultValue: '1.0.0', description: 'Version à déployer')
        choice(name: 'ENV', choices: ['staging', 'production'], description: 'Environnement')
    }

    stages {
        stage('Load Script') {
            steps {
                // Chargement du fichier Groovy externe
                script {
                    gscript = load 'script.groovy'
                }
            }
        }
        stage('Build') {
            steps {
                script {
                    gscript.buildApp()
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    gscript.testApp()
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    gscript.deployApp(params.VERSION, params.ENV)
                }
            }
        }
    }
}
