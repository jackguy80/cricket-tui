pipeline {
    agent any
    stages {
        stage('Setup Rust') {
            steps {
                sh '''
                    curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y
                    source $HOME/.cargo/env
                    rustc --version
                '''
            }
        }
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