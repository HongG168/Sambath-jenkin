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
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
                echo 'Tool: Junit or testNG'
            }
            post {
                success {
                    mail(
                        subject: "Unit and Integration Tests",
                        body: "Unit and Integration Tests stage is successful",
                        to: "babybear168888@gmail.com"
                    )
                }
                failure {
                    mail(
                        subject: "Unit and Integration Tests",
                        body: "The pipeline failed.",
                        to: "babybear168888@gmail.com"
                    )
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing the code with SonarQube...'
                echo 'Tool: SonarQube'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
                echo 'Tool: OWASP dependency check'
            }
            post {
                success {
                    mail(
                        subject: "Security scan",
                        body: "Security scan stage is successful",
                        to: "babybear168888@gmail.com"
                    )
                }
                failure {
                    mail(
                        subject: "Security scan",
                        body: "The pipeline failed.",
                        to: "babybear168888@gmail.com"
                    )
                }
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
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to Production environment...'
                echo 'Tool: AWS CLI'
            }
        }
    }

    post {
        success {
            mail(
                subject: "Pipeline Success: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: "The pipeline ${env.JOB_NAME} #${env.BUILD_NUMBER} was successful.",
                to: "babybear168888@gmail.com"
            )
        }
        failure {
            mail(
                subject: "Pipeline Failed: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: "The pipeline ${env.JOB_NAME} #${env.BUILD_NUMBER} failed.",
                to: "babybear168888@gmail.com"
            )
        }
    }
}
