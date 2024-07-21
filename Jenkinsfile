pipeline {
    agent any

    environment {
        PATH = 'C:\\Windows\\System32'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], userRemoteConfigs: [[url: 'https://github.com/lucas-castro-icts/android_jenkins.git']]])
            }
        }

        stage('Build') {
            steps {
                bat 'flutter --version'
            }
        }
    }
}
