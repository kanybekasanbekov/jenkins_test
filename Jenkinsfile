pipeline {
    agent any

    stages {
        stage('Run Python') {
            steps {
                sh 'python main.py'
            }
        }

        stage('Build C++') {
            steps {
                dir('build'){
                    sh 'cmake ..'
                    sh 'make'
                    sh './main'
                }
            }
        }
    }
}
