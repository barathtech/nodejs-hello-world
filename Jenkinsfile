 pipeline {
    agent any
    stages {
        stage('build') {
            steps { 
                sh'''apt pm2 index.js'''
                
            }
        }
        stage('Deploy') {
            steps{
              sshagent(credentials : ['barath']) {
              sh 'ssh -o StrictHostKeyChecking=no root@54.147.63.170'
              sh 'scp -p -r /var/lib/jenkins/workspace/demo root@54.147.63.170:/var/www/'
              }
            }
        }
    }
}
