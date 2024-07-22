pipeline {
    agent any

    environment {
        FLUTTER_PATH = 'C:\\flutter'
        PATH = "${FLUTTER_PATH};C:\\flutter\\.git;${env.PATH}"
    }

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], userRemoteConfigs: [[url: 'https://github.com/lucas-castro-icts/android_jenkins.git']]])
            }
        }

        stage('Install Dependencies') {
            steps {
                echo "${env.PATH}"
                bat 'flutter --version'
            }
        }
    }

    post {
        always {
            cleanWs()
        }
    }
}
