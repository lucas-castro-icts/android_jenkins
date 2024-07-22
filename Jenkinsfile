pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], userRemoteConfigs: [[url: 'https://github.com/lucas-castro-icts/android_jenkins.git']]])
            }
        }

        stage('Install Dependencies') {
            steps {
                bat '''
                    git --version
                    flutter
                '''
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
