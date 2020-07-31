pipeline {

  agent {
    label 'jenkins-slave-molecule'
  }

  stages {

    stage ('Get latest code') {
      steps {

        git {
           remote {
             github('test-owner/test-project')
             refspec('+refs/pull/*:refs/remotes/origin/pr/*')
           }
           branch('${sha1}')
        }
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

