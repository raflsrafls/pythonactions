pipeline {
    agent any
    
    stages {
        stage('install-pip-deps') {
            steps {
                powershell 'git clone https://github.com/mtararujs/python-greetings'

                powershell 'ls python-greetings'

                powershell 'pip install -r python-greetings\\requirements.txt'
                
                echo 'Installing PIP has started ...'
            }
        }
        stage('deploy-to-dev') {
            steps {

                powershell 'pm2 start python-greetings/app.py --name greetings-app-dev -p 7001'

                powershell 'pm2 delete all'

                echo 'Deployment to DEV has started..'
            }
        }
        stage('tests-on-dev') {
            steps {
                powershell 'git clone https://github.com/mtararujs/course-js-api-framework.git'

                powershell 'copy C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\pipelineldtest\\course-js-api-framework\\package.json C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\pipelineldtest\\ '

                powershell 'npm install'

                echo 'Testing on DEV has started..'
            }
        }
        stage('deploy-to-staging') {
            steps {
                powershell 'pm2 start python-greetings/app.py --name greetings-app-staging -p 7002'

                powershell 'pm2 delete all'

                echo 'Deployment to STG has started..'
            }
        }
        stage('tests-on-staging') {
            steps {

                powershell 'copy C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\pipelineldtest\\course-js-api-framework\\package.json C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\pipelineldtest\\ '

                powershell 'npm install'

                echo 'Testing on STG has started..'
            }
        }
        stage('deploy-to-preprod') {
            steps {

                powershell 'pm2 start python-greetings/app.py --name greetings-app-preprod -p 7003'

                powershell 'pm2 delete all'

                echo 'Deployment to PRD has started..'
            }
        }
        stage('tests-on-preprod') {
            steps {

                powershell 'copy C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\pipelineldtest\\course-js-api-framework\\package.json C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\pipelineldtest\\ '

                powershell 'npm install'

                echo 'Testing on PRD has started..'
            }
        }
        stage('deploy-to-prod') {
            steps {

                powershell 'pm2 start python-greetings/app.py --name greetings-app-prod -p 7004'

                powershell 'pm2 delete all'

                echo 'Deployment to PROD has started..'
            }
        }
        stage('tests-on-prod') {
            steps {

                powershell 'copy C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\pipelineldtest\\course-js-api-framework\\package.json C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\pipelineldtest\\ '

                powershell 'npm install'

                echo 'Testing on PROD has started..'
            }
        }
    }
}