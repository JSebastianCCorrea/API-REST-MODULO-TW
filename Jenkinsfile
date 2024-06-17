pipeline {
    agent any

    stages {
        stage('Clonacion del Repositorio') {
            steps {
                git branch: 'master', url: 'https://github.com/JSebastianCCorrea/API-REST-MODULO-TW'
            }
        }
        stage('Construccion de Docker image') {
            steps{
                script {
                    docker.build('myapp-modulo:v1', '.')
                }
            }
        }
        stage('Desplegar contenedores docker') {
            steps {
                script {
                    sh 'docker-compose up -d'
                }
            }
        }
    }

}