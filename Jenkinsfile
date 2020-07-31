pipeline {

  agent {
    label 'jenkins-slave-molecule'
  }

  stages {

    stage ('Get latest code') {
      steps {
        git branch: '${sha1}', url: 'https://github.com/gnekic/mycluster-gitops.git'
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

