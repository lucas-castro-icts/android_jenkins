pipeline {
    agent any

    environment {
        //     GIT_PATH = 'C:\\Program Files\\Git\\bin'
        FLUTTER_PATH = 'C:\\Users\\TBS\\fvm\\versions\\3.10.1\\bin'
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
                bat '''
                    flutter pub get
                '''
            }
        }

        stage('Build APK') {
            steps {
                bat 'flutter build apk --release'
            }
        }

        // stage('Archive APK') {
        //     steps {
        //         archiveArtifacts artifacts: 'build/app/outputs/flutter-apk/app-release.apk', allowEmptyArchive: true
        //     }
        // }
    }

    post {
        always {
            cleanWs()
        }
    }
}
