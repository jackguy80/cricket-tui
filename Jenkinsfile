pipeline {
    agent any
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
    post {
        always {
            // Example: Configure warning parsers for Rust/Clippy
            // step([$class: 'WarningsPublisher', ...])
        }
    }
}   