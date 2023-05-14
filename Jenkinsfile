pipeline {
    agent any

    stages {
        stage('install-pip-deps') {
            steps {
                script{
                    install()
                }
            }
        }
        stage('deploy-to-dev') {
            steps {
                script{
                    deploy("dev",7001)
                }
            }
        }
        stage('tests-on-dev') {
            steps {
                script{
                    test("dev")
                }
            }
        }
        stage('deploy-to-staging') {
            steps {
                script{
                    deploy("staging",7002)
                }
            }
        }
        stage('tests-on-staging') {
            steps {
                script{
                    test("staging")
                }
            }
        }
        stage('deploy-to-preprod') {
            steps {
                script{
                    deploy("preprod",7003)
                }
            }
        }
        stage('tests-on-preprod') {
            steps {
                script{
                    test("preprod")
                }
            }
        }
        stage('deploy-to-prod') {
            steps {
                script{
                    deploy("prod",7004)
                }
            }
        }
        stage('tests-on-prod') {
            steps {
                script{
                    test("prod")
                }
            }
        }
    }
}

def install() {
    echo "Installing required libraries"
    git branch: 'main', changelog: false, poll: false, url: 'https://github.com/mtararujs/python-greetings.git'
    bat "call pip install -r requirements.txt"
}

def deploy(String env, int port) {
    echo "Deploying into ${env}"
    git branch: 'main', changelog: false, poll: false, url: 'https://github.com/mtararujs/python-greetings.git'
    bat "call pm2 delete greetings-app-${env} & set \"ErrorLevel=0\""
    bat "call pm2 start app.py --name greetings-app-${env} -- --port ${port}"
}

def test(String env) {
    echo "Testing of programm from ${env}"
    git branch: 'main', changelog: false, poll: false, url: 'https://github.com/mtararujs/course-js-api-framework.git'
    bat "call npm install"
    bat "call npm run greetings greetings_${env}"
}
