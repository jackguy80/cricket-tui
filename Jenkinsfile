pipeline {
    agent {
        docker {
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
                sh 'cargo install cargo-test-junit && cargo test-junit --name report.xml'
            }
        }
        stage('Documentation') {
            steps {
                sh 'cargo doc'
            }
        }
    }
    post {
        always {
            archiveArtifacts artifacts: 'target/*/cricket-tui, target/doc/**/*, report.xml', fingerprint: true
        }
    }
}   