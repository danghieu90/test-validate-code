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
        echo "build URL is ${env.BUILD_URL}"
        script {
          def userInput = input(message: 'Success or error ?',
          parameters: [[$class: 'ChoiceParameterDefinition',
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

  stage('finish') {
    steps {
      cleanWs(cleanWhenSuccess: true, cleanWhenAborted: true, cleanWhenFailure: true, cleanWhenNotBuilt: true, cleanWhenUnstable: true, cleanupMatrixParent: true, deleteDirs: true, disableDeferredWipeout: true)
    }
  }

}
}
