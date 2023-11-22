@Library('my-shared-library') _

pipeline {
    agent any

    parameters {
        string(name: 'GIT_URL', description: 'GitHub Repository URL for Project A')
        string(name: 'IMAGE_NAME', description: 'Docker Image Name for Project A', defaultValue: 'projecta-image')
        string(name: 'PORT', description: 'Port for Project A', defaultValue: '8086')
    }

    stages {
        stage('Checkout') {
            steps {
                script {
                    commonFunctions.callCheckout(this, params.GIT_URL)
                }
            }
        }

        stage('Build Image') {
            steps {
                script {
                    commonFunctions.buildImage(this, params.IMAGE_NAME)
                }
            }
        }

        stage('Access Image Locally') {
            steps {
                script {
                    commonFunctions.accessImageLocally(this)
                }
            }
        }
    }
}
