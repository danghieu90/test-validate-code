pipeline {
  agent {
    docker {
      image 'php:7.3-cli-alpine'
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