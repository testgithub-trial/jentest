pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'jen', url: 'https://github.com/testgithub-trial/jentest.git']]])
            }
        }
        stage('Build') {
            steps {
                git branch: 'main', credentialsId: 'jen', url: 'https://github.com/testgithub-trial/jentest.git'
                bat 'python test.py'
            }
        }
        stage('Last stage') {
            steps {
                echo 'Completedddddd'
            }
        }
    }
}
