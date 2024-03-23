pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                echo "Webpack: building project"
                echo 'done'
            }
        }
        stage('test') {
            steps {
                echo 'Jest: running unit test'
                echo 'Jest: running intergration'
            }
            post {
                success {
                    emailext body: 'Test stage succeeded', 
                    subject: 'Test stage succeeded',
                    to: 'dakhoa0903@gmail.com'
                }
                failure {
                    emailext body: 'Test stage failed', 
                    subject: 'Test stage failed',
                    to: 'dakhoa0903@gmail.com',
                    attachLog: true
                }
            }

        }
        stage('code quality check') {
            steps {
                echo 'Eslint: check the quality of code'
                echo 'Prettier: check the quality of code'
                echo 'done'
            }
        }
        stage('security scan') {
            steps {
                echo 'Snyk: running security scan'
            }
            post {
                success {
                    emailext body: 'security scan succeeded', 
                    subject: 'security scan succeeded',
                    to: 'dakhoa0903@gmail.com'
                }
                failure {
                    emailext body: 'security scan failed', 
                    subject: 'security scan failed',
                    to: 'dakhoa0903@gmail.com',
                    attachLog: true
                }
            }
        }
        stage('deploy to staging') {
            steps {
                echo 'AWS EC2: deploy the application'
            }
        }
        stage('integration test on staging') {
            steps {
                echo 'running integration test on staging'
            }
        }
        stage('deploy to production') {
            steps {
                echo 'deploy the application to a AWS EC2'
            }
        }
    }
}