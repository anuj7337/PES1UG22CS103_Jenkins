pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM', 
                    branches: [[name: 'main']], 
                    userRemoteConfigs: [[url: ' https://github.com/anuj7337/PES1UG22CS103_Jenkins.git']]
                ])
            }
        }
        stage('Build') {
            steps {
                build 'PES1UG22CS103'
                sh 'g++ ./main/hello.cpp -o ./output'
            }
        }
        stage('Test') {
            steps {
                sh './output'
            }
        }
        stage('Deploy') {
            steps {
                echo 'deploy'
            }
        }
    }
    post {
        failure {
            error 'Pipeline failed'
        }
    }
}