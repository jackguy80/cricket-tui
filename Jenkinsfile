pipeline {
    agent {
        dockerContainer {
            image 'rust:latest'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'cargo build'
            }
        }
        stage('Test') {
            steps {
                sh 'cargo test'
            }
        }
    }
}   