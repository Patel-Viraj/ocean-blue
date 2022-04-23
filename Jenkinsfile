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
        sh '''rsync -zhvr . ubuntu@18.234.230.50:/home/ubuntu/viraj/
'''
      }
    }

    stage('Install Packaged') {
      steps {
        sh 'ssh -t ubuntu@18.234.230.50 \'cd /home/ubuntu/viraj\' '
      }
    }

    stage('Start Application') {
      steps {
        sh 'ssh -t ubuntu@18.234.230.50 "cd /home/ubuntu/viraj/ && pwd" '
      }
    }

  }
}