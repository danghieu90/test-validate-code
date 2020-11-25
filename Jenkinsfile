pipeline {
  agent {
    docker {
      image 'hieudangz/php-fpm:7.4'
    }

  }
  stages {
    stage('init') {
      parallel {
        stage('init') {
          steps {
            sh 'whoami'
          }
        }

        stage('init 2') {
          steps {
            sh 'pwd'
          }
        }

      }
    }

  }
}