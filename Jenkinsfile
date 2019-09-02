pipeline {
    agent { docker { image 'python:3.5.1' } }
    stages {
        stage('build') {
            steps {
                echo "Iniciando construcción"
                sh 'python hola.py'
                echo "Finalizando construcción"
            }
        }
    }
}
