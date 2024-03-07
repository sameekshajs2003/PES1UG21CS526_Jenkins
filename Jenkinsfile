pipeline {
    agent any

    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM',
                          branches: [[name: 'main']],
                          userRemoteConfigs: [[url: 'https://github.com/sameekshajs2003/PES1UG21CS526_Jenkins.git']]])
            }
        }

        stage('Build') {
            steps {
                build job: 'PES1UG21CS526-1'
                sh 'g++ Jenkins_lab-main/main/main.cpp -o output'
            }
        }

        stage('Test') {
            steps {
                sh './Jenkins_lab-main/main/output'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deployment step'
            }
        }
    }

    post {
        failure {
            error 'Pipeline failed'
        }
    }
}
