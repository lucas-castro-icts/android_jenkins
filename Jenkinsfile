pipeline {
    agent any

    environment {
        // GIT_PATH = 'C:\\Program Files\\Git\\bin\\git.exe;C:\\Program Files\\Git\\cmd;C:\\Windows\\System32'
        // FLUTTER_PATH = 'C:\\flutter\\bin'
        // PATH = ";${GIT_PATH};${FLUTTER_PATH};${SYSTEM_PATH};${env.PATH}"
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

        // stage('Build APK') {
        //     steps {
        //         bat 'flutter --version'
        //     }
        // }

    // stage('Archive APK') {
    //     steps {
    //         archiveArtifacts artifacts: 'build/app/outputs/flutter-apk/app-release.apk', allowEmptyArchive: true
    //     }
    // }
    }

    // post {
    //     always {
    //         cleanWs()
    //     }
    // }
}
