pipeline {
    agent any

    environment {
        FLUTTER_PATH = "C:\\Users\\TBS\\flutter\\bin"
        DART_SDK = "C:\\tools\\dart-sdk\\bin"
        PATH = "${FLUTTER_PATH};${DART_SDK};${env.PATH}"
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

