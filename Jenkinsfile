pipeline {
    agent any

    environment {
        DIRECTORY_PATH = '/'
        TESTING_ENVIRONMENT = 'testenv'
        PRODUCTION_ENVIRONMENT = 'Khoa Env'
    }
    
    stages {
        stage('build') {
            steps {
                echo "fetch the source code from the directory path ${DIRECTORY_PATH} specified by the environment variable"
                echo 'compile the code and generate any necessary artifacts'
            }
        }
        stage('test') {
            steps {
                echo 'unit test'
                echo 'integration test'
            }
        }
        stage('code quality check') {
            steps {
                echo 'check the quality of code'
            }
        }
        stage('deploy') {
            steps {
                echo 'deploy the application to a testing environment specified by the environment variable'
            }
        }
        stage('approval') {
            steps {
                sh 'sleep 10'
            }
        }
        stage('deploy to production') {
            steps {
                echo 'deploying to ${PRODUCTION_ENVIRONMENT}'
            }
        }
    }
}