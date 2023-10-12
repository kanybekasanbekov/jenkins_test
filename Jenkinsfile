pipeline {
    agent any

    stages {
        stage('Chec Path'){
            steps {
                sh 'pwd'
                sh 'ls -la'
            }
        }
        stage('Run Python') {
            steps {
                sh 'python my_python_script.py'
            }
        }

        stage('Build C++') {
            steps {
                sh 'cmake .'
                sh 'make'
                sh './main'
            }
        }
    }
}
