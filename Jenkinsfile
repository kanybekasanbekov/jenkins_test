pipeline {
    agent any

    stages {
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
