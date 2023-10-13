pipeline {
    agent {
        docker {
            // image 'mobilint/qbcompiler:latest'
            image 'pytorch/pytorch:latest'
            // args '-u root'
        }
    }
    stages {
        stage('Confirm docker'){
            steps {
                sh 'pwd'
                sh 'ls -al'
                sh 'pip --version'
                sh 'pip list'
                // sh 'pip show tvm'
                sh 'python --version'
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
