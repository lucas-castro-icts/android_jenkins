pipeline {
    agent any

    environment {
        GIT_PATH = 'C:\\Program Files\\Git\\cmd;C:\\Program Files\\Git\\bin;C:\\Program Files\\Git\\bin\\git.exe;'
        FLUTTER_PATH = 'C:\\Users\\TBS\\fvm\\default\\bin'
        SYSTEM_PATH = 'C:\\Windows\\System32'
        PATH = "${GIT_PATH};${FLUTTER_PATH};${SYSTEM_PATH};${env.PATH}"
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
                            git --versions
                            flutter --version
                        '''
                    }
                }
            }
        }
    }
}
