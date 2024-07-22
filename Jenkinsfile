pipeline {
    agent any

    environment {
        FLUTTER_PATH = 'C:\\flutter'
        PATH = "${FLUTTER_PATH};${env.PATH}"
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
                            flutter --version
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
