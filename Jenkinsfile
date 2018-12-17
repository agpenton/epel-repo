pipeline {
  agent {
    docker {
      image 'geerlingguy/docker-centos7-ansible:latest'
    }

  }
  stages {
    stage('Test') {
      parallel {
        stage('Test') {
          steps {
            sh 'mkdir -p ${PWD}/tests'
            sh 'wget -O ${PWD}/tests/test.sh https://gist.githubusercontent.com/geerlingguy/73ef1e5ee45d8694570f334be385e181/raw/'
            sh 'chmod +x ${PWD}/tests/test.sh'
            sh '${PWD}/tests/test.sh'
          }
        }
        stage('') {
          steps {
            echo 'failed...something when wrong!!!'
          }
        }
      }
    }
    stage('') {
      steps {
        echo 'all good!!!'
      }
    }
  }
}