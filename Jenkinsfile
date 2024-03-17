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

        stage('let\'s build the frontend docker file'){
            steps{
                sh 'cd ResumeBuilderAngular && docker build -t narsss1234/resumeai-frontend:latest .'
            }
        }

        stage('install Backend dependencies'){
            steps{
                sh 'cd ResumeBuilderBackend && npm install --force && sudo npm i -g typescript ng'
            }
        }

        stage('let\'s build the backend docker file'){
            steps{
                sh 'cd ResumeBuilderBackend && docker build -t narsss1234/resumeai-backend:latest .'
            }
        }

        stage('Push the images'){
            steps{
                sh 'docker push narsss1234/resumeai-frontend:latest'
                sh 'docker push narsss1234/resumeai-backend:latest'
            }
        }

        stage('update kube config'){
            steps{
                sh 'aws eks update-kubeconfig --region ap-south-1 --name resumeai-new'
            }
        }

        stage('let\'s apply the kube files or use helm - either way'){
            steps{
                sh 'cd kubernetes-files && kubectl apply -f .'
            }
        }
    }
}