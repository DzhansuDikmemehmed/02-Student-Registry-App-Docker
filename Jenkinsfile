pipeline {
    agent any
    stages {
        stage('NPM Install') {
            steps {
                bat 'npm install'
            }
        }
        stage('Parallel Execution') {
            parallel {
                stage('Run npm audit tests') {
                    steps {
                        bat 'npm audit'
                    }
                }
                stage('Execute tests') {
                    steps {
                        bat 'npm test'
                    }
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploy to Staging'
            }
        }
        stage('Approval for Production') {
            steps {
                script {
                    input message: 'Approve deployment to production?', ok: 'Proceed'
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploy to Production'
            }
        }
    }
}
