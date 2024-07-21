pipeline {
    agent any

    environment {
        GIT_PATH = 'C:\\Program Files\\Git\\bin'
        FLUTTER_PATH = ';C:\\ProgramData\\chocolatey\\bin'
        SYSTEM_PATH = 'C:\\Windows\\System32'
        PATHH = "${GIT_PATH};${FLUTTER_PATH};${SYSTEM_PATH};${env.PATH}"
    }

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], userRemoteConfigs: [[url: 'https://github.com/lucas-castro-icts/android_jenkins.git']]])
            }
        }

        stage('Fetch') {
            steps {
                withEnv(["PATH=${env.PATHH}"]) {
                    dir('app') {
                        bat '''
                            git --version
                            fvm flutter
                        '''
                    }
                }
            }
        }
    }
}
