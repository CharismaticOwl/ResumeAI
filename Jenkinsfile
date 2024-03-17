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
                sh 'cd ResumeBuilderAngular && sudo npm i -g ng && sudo npm test'
            }
        }
    }
}