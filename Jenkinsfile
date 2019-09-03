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
        agent {docker { image 'qnib/pytest'} }
        stage('Test') {
            steps {
                sh 'pytest --verbose --junit-xml test-reports/results.xml test_sample.py'
            }
            post {
                always {
                    junit 'test-reports/results.xml'
                }
            }
        }
    }
}
