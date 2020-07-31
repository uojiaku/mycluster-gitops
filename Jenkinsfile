pipeline {

  agent {
    label 'jenkins-slave-molecule'
  }

  stages {

    stage ('Get latest code') {
      steps {

        git {
           url('https://github.com/gnekic/mycluster-gitops.git')
           remote {
             github('gnekic/mycluster-gitops')
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

