pipeline {
    agent any

    stages {
        stage('install-pip-deps') {
            steps {
                echo 'Installing required libraries'
            }
        }
        stage('deploy-to-dev') {
            steps {
                echo 'Deploying into dev environment'
            }
        }
        stage('tests-on-dev') {
            steps {
                echo 'Testing of programm from dev environment'
            }
        }
        stage('deploy-to-staging') {
            steps {
                echo 'Deploying into staging'
            }
        }
        stage('tests-on-staging') {
            steps {
                echo 'Testing of programm from staging'
            }
        }
        stage('deploy-to-preprod') {
            steps {
                echo 'Deploying into preprodaction'
            }
        }
        stage('tests-on-preprod') {
            steps {
                echo 'Testing of programm from preprodaction'
            }
        }
        stage('deploy-to-prod') {
            steps {
                echo 'Deploying into prodaction'
            }
        }
        stage('tests-on-prod') {
            steps {
                echo 'Testing of programm from prodaction'
            }
        }
    }
}
