pipeline {
  agent any
  stages {
    stage('First Stage') {
      steps {
        echo 'Hi, this is Github User 003'
        sh '''
        ls -ltr
        pwd
        whoami
        '''
      }
    }
    stage('Deploy Stage') {
      steps {
        retry(3) {
          sh './flakey-deploy.sh'
        }
      }
    }
  }  
}