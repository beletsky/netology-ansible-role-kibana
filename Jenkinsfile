pipeline {
    agent any
    stages {
        stage('checkout') {
            steps {
                git credentialsId: 'GitHub-beletsky', url: 'https://github.com/beletsky/netology-ansible-role-kibana'
            }
        }
        stage('install requirements') {
            steps {
                sh 'pip3 install -r test-requirements.txt'
            }
        }
        stage('run molecule') {
            steps {
                sh 'molecule test'
            }
        }
    }
}
