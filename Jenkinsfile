pipeline {
    agent any

    environment {
        FLUTTER_PATH = "C:\\Users\\TBS\\flutter\\bin"
        PATH = "${FLUTTER_PATH};${env.PATH}"
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

