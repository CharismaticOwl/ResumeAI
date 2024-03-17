pipeline{
    agent any

    stages{

        stage('Fetch the code'){
            steps{
                git branch: 'main', url: 'https://github.com/CharismaticOwl/ResumeAI'
            }
        }

        stage('Test Frontend'){
            steps{
                sh 'cd ResumeBuilderAngular && npm install --force && sudo npm i -g ng @angular/cli && sudo npm test'
            }
        }

        stage('let\'s build the docker file'){
            steps{
                sh 'echo workINprogress'
            }
        }
    }
}