pipeline {
    agent any

    environment {
        GIT_PATH = 'C:\\Program Files\\Git\\bin'
        FLUTTER_PATH = 'C:\\Users\\TBS\\fvm\\versions\\stable\\bin'
        PATH = "${GIT_PATH};${FLUTTER_PATH};${env.PATH}"
    }

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], userRemoteConfigs: [[url: 'https://github.com/lucas-castro-icts/android_jenkins.git']]])
            }
        }

        stage('Fetch') {
            steps {
                withEnv(["PATH=${env.PATH}"]) {
                    dir('app') {
                        bat '''
                            git --version
                            flutter --version
                        '''
                    }
                }
            }
        }
    }
}
