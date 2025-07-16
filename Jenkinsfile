pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: 'main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/vignesh-110592/JenkinsPipeline.git']]])
            }
        }
        stage('Build') {
            steps {
                git branch: 'main', url: 'https://github.com/vignesh-110592/JenkinsPythonTest.git'
                sh 'python3 ops.py'
            }
        }
        stage('Test') {
            steps {
                git branch: 'main', url: 'https://github.com/vignesh-110592/JenkinsPythonTest.git'
                sh 'python3 -m pytest'
            }
        }
    }
}
