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
                sh 'cargo test'
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
            archiveArtifacts artifacts: 'target/**/cricket-tui', fingerprint: true
            archiveArtifacts artifacts: 'target/doc/**/*', fingerprint: true
        }
    }
}   