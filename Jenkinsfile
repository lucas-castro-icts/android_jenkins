pipeline {
    agent any

    environment {
        PATH = 'C:\\Windows\\System32;C:\\Users\\TBS\\fvm\\default\\bin'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], userRemoteConfigs: [[url: 'https://github.com/lucas-castro-icts/android_jenkins.git']]])
            }
        }

        stage('Fetch') {
            steps {
                dir('app') {
                    bat label: '', script: 'flutter --version'
                }
            }
        }
    }
}
