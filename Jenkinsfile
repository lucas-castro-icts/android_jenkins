pipeline {
    agent any

    environment {
        SYSTEM_PATH = 'C:\\Windows\\System32'
        FLUTTER_PATH = 'C:\\flutter\\bin'
        PATH = "${FLUTTER_PATH};;${SYSTEM_PATH};${env.PATH}"
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
                        bat '''
                            git --version
                            flutter
                        '''
                    }
                }
            }
        }
    }

// post {
//     always {
//         cleanWs()
//     }
// }
}
