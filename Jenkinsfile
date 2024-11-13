pipeline {
    agent any

    stages {
        stage('checkout') {
            steps {
                git 'https://github.com/CharanReddy129/game_2048.git'
            }
        }
        stage("build and pushing image"){
            steps{
                withDockerRegistry(credentialsId: 'DockerHub' , url: 'https://index.docker.io/v1/') {
                    sh "docker build -t charanreddy12/game-2048:latest ."
                    sh "docker push charanreddy12/game-2048:latest"
                }
            }
        }
        stage("deploying k8s objects"){
            steps{
                ansiblePlaybook credentialsId: 'charan-user', disableHostKeyChecking: true, installation: 'ansible', inventory: '/etc/ansible/hosts', playbook: './playbook.yaml', vaultTmpPath: ''
            }
        }
    }
}
