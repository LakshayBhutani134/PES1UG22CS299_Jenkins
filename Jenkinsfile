pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM',
                    branches: [[name: '*/main']],
                    userRemoteConfigs: [[url: 'https://github.com/LakshayBhutani134/PES1UG22CS299_Jenkins.git']]
                ])
            }
        }

        stage('Build') {
            steps {
                build 'PES1UG22CS299-1'
                sh 'g++ one.cpp -o output'
            }
        }

    }

    post {
        failure {
            error 'Pipeline failed'
        }
    }
}