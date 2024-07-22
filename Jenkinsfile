pipeline {
    agent any

    environment {
        // FLUTTER_PATH = 'C:\\Windows\\System32'
        // PATH = "${FLUTTER_PATH};${env.PATH}"
        FLUTTER_VERSION = '3.19.2' 
        FLUTTER_HOME = "${env.WORKSPACE}/flutter"
        PATH = "${FLUTTER_HOME}/bin:${env.PATH}"
    }

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], userRemoteConfigs: [[url: 'https://github.com/lucas-castro-icts/android_jenkins.git']]])
            }
        }

        stage('Install Dependencies') {
            steps {
                // withEnv(["PATH=${env.PATH}"]) {
                //     dir('app') {
                //         echo "${env.PATH}"
                //         bat '''
                //             git --version
                //             flutter
                //         '''
                //     }
                // }
                bat '''
                    if [ ! -d "${FLUTTER_HOME}" ]; then
                        curl -o flutter.tar.xz https://storage.googleapis.com/flutter_infra_release/releases/stable/linux/flutter_linux_${FLUTTER_VERSION}-stable.tar.xz
                        tar xf flutter.tar.xz
                        mv flutter ${FLUTTER_HOME}
                    fi
                    '''
            }
        }
    }

// post {
//     always {
//         cleanWs()
//     }
// }
}
