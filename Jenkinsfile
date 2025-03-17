pipeline {
    agent any

    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM', 
                    branches: [[name: '*/main']], 
                    userRemoteConfigs: [[url: 'https://github.com/Vismaya-Murali/PES1UG22CS706_Jenkins']]
                ])
            }
        }

        stage('Build') {
            steps {
                build 'PES1UG22CS706-1'  
                sh 'g++ main/hello.cpp -o output'
            }
        }

        stage('Test') {
            steps {
                sh './output'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application'
            }
        }
    }

    post {
        failure {
            error 'Pipeline failed'
        }
    }
}
