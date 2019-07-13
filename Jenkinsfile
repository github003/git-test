pipeline {
  agent any

  environment {
    DISABLE_AUTH = 'true'
    DB_ENGINE    = 'sqlite'
  }

  stages {
    stage('Confirmation Step') {
      steps {
        input('Do you want to proceed?')
        sh 'printenv'
      }
    }
    stage('If Proceed is clicked') {
      steps {
        print('hello')
      }
    }
  }
  post {
    always {
        echo 'This will always run'
    }
    success {
        echo 'This will run only if successful'
    }
    failure {
      mail to: 'ksandy003@gmail.com',
          subject: "Failed Pipeline: ${currentBuild.fullDisplayName}",
          body: "Something is wrong with ${env.BUILD_URL}"
    }
    unstable {
        echo 'This will run only if the run was marked as unstable'
    }
    changed {
        echo 'This will run only if the state of the Pipeline has changed'
        echo 'For example, if the Pipeline was previously failing but is now successful'
    }        
  }  
}