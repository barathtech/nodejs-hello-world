 pipeline {
    agent any
    stages {
        stage('build') {
            steps { 
                sh'''sudo apt install nginx -y'''
                
            }
        }
        stage('Deploy') {
            steps{
              sshagent(credentials : ['ssh-key']) {
              sh 'ssh -o StrictHostKeyChecking=no ubuntu@192.168.1.223'
              sh 'scp -p -r /var/lib/jenkins/workspace/demo ubuntut@192.168.1.223:/var/www/'
              sh 'nginx -v'
              }
            }
        }
    }
}
