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
        sh '''pwd rsync -zhvr . ubuntu@3.239.180.46:/home/ubuntu/viraj/
'''
      }
    }

    stage('Install Packaged') {
      steps {
        sh 'pwd ssh -t ubuntu@3.239.180.46 \'cd /home/ubuntu/viraj\' '
      }
    }

    stage('Start Application') {
      steps {
        sh 'pwd ssh -t ubuntu@3.239.180.46 "cd /home/ubuntu/viraj/" pwd'
      }
    }

  }
}