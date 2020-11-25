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
             def userInput = input(message: 'Success or error ?',
             parameters: [[$class: 'ChoiceParameterDefinition', defaultValue: 'strDef', 
                description:'describing choices', name:'nameChoice', choices: "Success\nError"]
             ])

            if( "${userInput}" == "Success"){
                currentBuild.result = 'SUCCESS'
            } else {
                currentBuild.result = 'FAILURE'
            }
        }
      }
    }

  }
}
