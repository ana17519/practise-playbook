pipeline {
    agent {
        label "linux"
    }
    stages {
        stage('Checkout repo'){
            steps {
                git branch: 'feature/jenkins', credentialsId: 'da5cf165-10a6-4a61-a089-d04b6a045510', url: 'git@github.com:ana17519/practise-playbook.git'
            }
        }
        stage ('Prepare for molecule'){
            steps {
                sh 'pip3 install -r requirements.txt'
            }
        }
        stage('Run molecule'){
            steps{
                dir('vector-role'){
                    sh 'molecule init scenario'
                    sh 'molecule test'
                }
            }
        }
    }
}