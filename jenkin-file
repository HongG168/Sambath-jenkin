pipeline {
    agent any
    environment {
        DIRECTORY_PATH = '/path/to/code/directory' // Replace with actual path
        TESTING_ENVIRONMENT = 'TestingEnvironment'
        PRODUCTION_ENVIRONMENT = 'Reachsambath Production'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building the project...'
                echo 'Tool: mavern'
                }
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
                echo 'Tool Junit or testNG'
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing the code with SonarQube...'
                echo 'Tool: SonarQube.'
                }
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
                echo 'Tool: OWASP dependency check'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to Staging environment...'
                echo 'Tool: AWS CLI or other deployment'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on the Staging environment...'
                echo 'Tool: selenium'
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to Production environment...'
                echo 'Tool: AWS CLI'
            }
        }
    }

    post {
        success {
            emailext(
                main subject: "Pipeline Success: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                     body: "The pipeline ${env.JOB_NAME} #${env.BUILD_NUMBER} was successful.",
                     to: "Reachsambath14@gmail.com",
                    
            )
        }
        failure {
            emailext(
                main subject: "Pipeline Failed: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                     body: "The pipeline ${env.JOB_NAME} #${env.BUILD_NUMBER} failed.",
                     to: "Reachsambath14@gmail.com",
                    
            )
        }
    }
}
