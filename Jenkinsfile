pipeline {
    agent any

    environment {
        GIT_PATH = 'C:\\Program Files\\Git\\bin'
        FLUTTER_PATH = 'C:\\ProgramData\\chocolatey\\bin;C:\\Users\\TBS\fvm\\default\\bin\\flutter'
        SYSTEM_PATH = 'C:\\Windows\\System32'
        PATH = "${SYSTEM_PATH};${GIT_PATH};${FLUTTER_PATH};${env.PATH}"
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
                            fvm flutter
                        '''
                    }
                }
            }
        }
    }
}
