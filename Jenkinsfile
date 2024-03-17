pipeline{
    agent any

    stages{

        stage('Fetch the code'){
            steps{
                git branch: 'main', url: 'https://github.com/CharismaticOwl/ResumeAI'
            }
        }

        stage('install Frontend dependencies'){
            steps{
                sh 'cd ResumeBuilderAngular && npm install --force && sudo npm i -g ng @angular/cli'
            }
        }

        stage('let\'s build the docker file'){
            steps{
                sh 'pwd && ls'
            }
        }
    }
}