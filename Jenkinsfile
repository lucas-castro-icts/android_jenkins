pipeline {
    agent any

    environment {
        PATH = "$PATH:C:\\Users\\TBS\\fvm\\default\\bin"
    }

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], userRemoteConfigs: [[url: 'https://github.com/lucas-castro-icts/android_jenkins.git']]])
            }
        }

        stage('Fetch') {
            steps{
                bat '$PATH; dart pub get'
            }
        } 
    }
}
