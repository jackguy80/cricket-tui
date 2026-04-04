pipeline {
    agent {
        docker {
            image 'rust:latest'
            args '-v /etc/passwd:/etc/passwd' // Fixes UID mismatch errors
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