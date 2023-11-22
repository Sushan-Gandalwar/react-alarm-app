pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
               
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Sushan-Gandalwar/react-alarm-app.git']])
                sh 'echo "Building the project"'
            }
        }

        stage('build image') {
            steps {
                script {
                    sh 'docker build -t jaydeep .'
                }
            }
        }
        stage('access image locally'){
            steps{
                script{
                    sh 'docker run -p 8085:3000 jaydeep'
                }
            }
        }

    }
}

