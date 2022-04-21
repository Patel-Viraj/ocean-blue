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
        sh '''pwd
ssh -t ubuntu@3.85.213.81

'''
      }
    }

    stage('Install Packaged') {
      steps {
        sh 'ssh -t ubuntu@3.85.213.81 \'cd /home/ubuntu/viraj && npm i\''
      }
    }

    stage('Start Application') {
      steps {
        sh 'ssh -t ubuntu@3.85.213.81 "cd /home/ubuntu/viraj/ && pm2 restart app.js"'
      }
    }

  }
}