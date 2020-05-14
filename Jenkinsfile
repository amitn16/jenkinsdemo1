pipeline {
    agent none
    stages {
        stage('Back-end') {
            agent {
                docker { image 'maven:3-alpine' }
            }
            steps {
                sh 'mvn --version'
            }
        }
        stage('Front-end') {
            agent {
                docker { image 'node:7-alpine' }
            }
            steps {
                sh 'node --version'
            }
        }
		stage("ssh-agent"){
			steps {
				script {
				sshagent (credentials: ['59d5c062-6674-4484-9669-7136eeea6336']) {
				sh 'ssh -o StrictHostKeyChecking=no -l amit 192.168.1.109 uname -a'
					}
				}
			}
		}
	}
}
