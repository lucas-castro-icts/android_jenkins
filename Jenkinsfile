pipeline {
    agent any

    environment {
        GIT_PATH = 'C:\\Program Files\\Git\\bin'
        FLUTTER_PATH = 'C:\\Users\\TBS\\fvm\\default\\bin'
        PATH = "${env.GIT_PATH};${env.FLUTTER_PATH};${env.PATH}"
    }

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], userRemoteConfigs: [[url: 'https://github.com/lucas-castro-icts/android_jenkins.git']]])
            }
        }

        stage('Build') {
            steps {
                powershell '''
                    $env:Path += ";C:\\Program Files\\Git\\bin;C:\\Users\\TBS\\fvm\\default\\bin"
                    flutter doctor -v
                '''
            }
        }
    }
}
