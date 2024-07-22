pipeline {
    agent any

    environment {
        FLUTTER_PATH = '/flutter/bin'
        PATH = "${FLUTTER_PATH};${SYSTEM_PATH};${env.PATH}"
    }

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], userRemoteConfigs: [[url: 'https://github.com/lucas-castro-icts/android_jenkins.git']]])
            }
        }

        stage('Install Dependencies') {
            steps {
                withEnv(["PATH=${env.PATH}"]) {
                    dir('app') {
                        echo "${env.PATH}"
                        bat '''
                            git --version
                            flutter
                        '''
                    }
                }
            }
        }
    }

post {
    always {
        cleanWs()
    }
}
}
