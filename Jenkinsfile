pipeline {

  agent {
    label 'jenkins-slave-molecule'
  }

  stages {

    stage ('Get latest code') {
      steps {
        checkout scm
      }
    }

    stage ('Molecule test') {
      steps {
        sh '''
          molecule test
        '''
      }
    }

  }

}

