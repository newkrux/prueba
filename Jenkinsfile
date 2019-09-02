pipeline {
    agent { docker { image 'python:3.5.1' } }
    stages {
        stage('Initialize'){
            def dockerHome = tool 'docker'
            env.PATH = "${dockerHome}/bin:${env.PATH}"
        }
        stage('build') {
            steps {
                echo "Iniciando construcción"
                sh 'python hola.py'
                echo "Finalizando construcción"
            }
        }
    }
}
