pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], userRemoteConfigs: [[url: 'https://github.com/lucas-castro-icts/android_jenkins.git']]])
            }
        }

        stage('Build') {
            steps {
                powershell '''
                    $env:Path += ";C:\\Users\\TBS\\fvm\\default\\bin"
                    flutter doctor -v
                '''
            }
        }
    }
}
