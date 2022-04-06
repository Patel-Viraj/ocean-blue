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
        sh 'rsync -zhvr . ubuntu@54.160.236.91:/home/ubuntu/viraj/'
      }
    }

    stage('Install Packaged') {
      steps {
        sh 'ssh -t ubuntu@54.160.236.91 \'cd /home/ubuntu/viraj && npm i\''
      }
    }

  }
}