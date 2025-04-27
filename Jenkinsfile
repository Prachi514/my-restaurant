pipeline {
    agent any

    environment {
        DOCKERHUB_CREDENTIALS = 'dockerhub-creds'
        DOCKERHUB_USERNAME = 'prachi333'
        IMAGE_NAME = 'prachi333/app'
        IMAGE_TAG = 'latest'
    }

    stages {
        stage('clone Repository') {
            steps {
                 git branch: 'main', url: 'https://github.com/Prachi514/my-restaurant.git'
            }
        }
         stage('List Files') {
            steps {
                bat 'dir' // Windows
                // OR for Linux: sh 'ls'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat "docker build -t  prachi333/app ."
            }
        }
    } // <-- this was missing: closes the 'stages' block

    post {
        always {
            echo 'Pipeline finished!'
        }
    }
}
