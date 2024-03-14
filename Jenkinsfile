pipeline{
    agent { docker { image 'node:12-alpine' } }

    stages{

        stage('Fetch the code'){
            steps{
                git branch: 'main', url: 'https://github.com/CharismaticOwl/ResumeAI'
            }
        }

        stage('Test Frontend'){
            steps{
                sh 'cd ResumeBuilderAngular && npm i -g ng && npm test'
            }
        }
    }
}