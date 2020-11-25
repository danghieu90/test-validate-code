pipeline {
  agent {
    docker {
      image 'codecheck:latest'
    }

  }
  stages {
    stage('init') {
      steps {
        sh 'pwd && whoami && id -u && id -g'
      }
    }

  }
}