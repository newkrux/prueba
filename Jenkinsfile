pipeline {
    agent none 
    
    stages {
        stage('build') {
            agent { docker { image 'python:3.5.1' } }
            steps {
                echo "Iniciando construcción"
                sh 'python hola.py'
                echo "Finalizando construcción"
            }
        }
        stage('Test') {
            agent {docker { image 'qnib/pytest'} }
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
