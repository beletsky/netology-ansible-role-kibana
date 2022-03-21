pipeline {
    agent any
    stages {
        stage('checkout') {
            steps {
                dir('ansible-role-kibana') {
                    git credentialsId: 'GitHub-beletsky', url: 'https://github.com/beletsky/netology-ansible-role-kibana'
                }
            }
        }
        stage('install requirements') {
            steps {
                dir('ansible-role-kibana') {
                    sh 'pip3 install -r test-requirements.txt'
                }
            }
        }
        stage('run molecule') {
            steps {
                dir('ansible-role-kibana') {
                    sh 'molecule test'
                }
            }
        }
    }
}
