pipeline {
    agent any
    triggers {                      
        cron('* * * * *')                   
    }
    stages {
        stage ('version control system') {
            steps {
                git branch: 'main', url: 'https://github.com/ziyad-ansari/saleor.git'
            }
        }
        stage ('docker image build') {   
            steps {
                sh 'docker image build -t ansziyad5/saleor-core:DEV .'
            }
        }
        stage ('push to registry') {
            steps {
                sh 'docker image push ansziyad5/saleor-core:DEV'
            }
        }
    }
}