pipeline {
  agent {
    docker {
      image 'codecheck:latest'
    }

  }
  stages {
    stage('init') {
      parallel {
        stage('init') {
          steps {
            sh 'pwd && whoami && id -u && id -g'
          }
        }

        stage('init 2') {
          steps {
            sh 'ls -al'
          }
        }

      }
    }

  }
}