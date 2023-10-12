pipeline {
    agent {
        docker {
            image 'mobilint/qbcompiler:latest'
            args '-u root'
        }
    }
    stages {
        stage('Confirm docker'){
            steps {
                sh 'pip show tvm'
            }
        }

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
