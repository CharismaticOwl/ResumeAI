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
                sh 'cd ResumeBuilderAngular && sudo npm i -g ng @angular/cli @angular-devkit/build-angular @angular/compiler-cli typescript --save-prod && sudo npm test'
            }
        }
    }
}