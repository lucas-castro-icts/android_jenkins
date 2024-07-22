pipeline {
    agent any

    environment {
        PATH = "${env.PATH}"
    }

    stages {
        stage('Checkout') {
            steps {
                    checkout([$class: 'GitSCM', branches: [[name: '*/master']], userRemoteConfigs: [[url: 'https://github.com/lucas-castro-icts/android_jenkins.git']]])
            }
        }

            steps {
                echo "${env.PATH}"
                bat "flutter --version"
            }
    }
}

