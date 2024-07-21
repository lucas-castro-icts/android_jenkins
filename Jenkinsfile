pipeline {
    agent any

    environment {
        PATH = 'C:\\Windows\\System32'
        GIT_PATH = 'C:\\Program Files\\Git\\bin'
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
                    bat label: '', script: 'C:\\Windows\\System32; C:\\Program Files\\Git\\bin git --version'
                }
            }
        }
    }
}
