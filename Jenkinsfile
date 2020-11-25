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

    stage('test') {
      steps {
        script {
             def userInput = input(message: 'Merge to?',
             parameters: [[$class: 'ChoiceParameterDefinition', defaultValue: 'strDef', 
                description:'describing choices', name:'nameChoice', choices: "QA\nUAT\nProduction\nDevelop\nMaster"]
             ])

            if( "${userInput}" == "Master"){
                stage('master') {
                  steps {
                    sh 'echo master'
                  }
                }
              stage('develop') {
                  steps {
                    sh 'echo develop'
                  }
                }
            } else {
                //do something else
            }
        }
      }
    }

  }
}
