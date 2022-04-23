pipeline {
  agent any
  stages {
    stage('test') {
      parallel {
        stage('test') {
          steps {
            echo 'testing'
            sh 'echo "testing"'
          }
        }

        stage('version check') {
          steps {
            sh '''git --version
                  aws --version'''
          }
        }

      }
    }

    stage('copy to ec2') {
      steps {
        sh 'pwd'
      }
    }

    stage('Install Packaged') {
      steps {
        sh 'ssh -o StrictHostKeyChecking=no ubuntu@18.234.230.50 \'cd /home/ubuntu/viraj && npm i\' '
      }
    }

    stage('Start Application') {
      steps {
        sh 'ssh -t ubuntu@18.234.230.50 "cd /home/ubuntu/viraj/ && pm2 restart" '
      }
    }

  }
}