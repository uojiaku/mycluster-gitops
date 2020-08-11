pipeline {

  agent {
    label 'jenkins-agent-ansible'
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

