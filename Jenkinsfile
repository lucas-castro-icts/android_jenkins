pipeline {
    agent any

    environment {
        PATH = "${env.PATH}"
    }

    stages {
        stage('Git clone') {
            steps {
                    checkout([$class: 'GitSCM', branches: [[name: '*/master']], userRemoteConfigs: [[url: 'https://github.com/lucas-castro-icts/android_jenkins.git']]])
            }
        }

        stage('Checkout') {
            steps {
                echo "${env.PATH}"
                bat "flutter --version"
            }
        }
    }
}

