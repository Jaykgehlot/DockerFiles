pipeline {
  agent any 

  stages {

    stage('building') {
      steps {
        echo ' The Code will be now ne built into an artifact'
      }
    }
    stage('Artifact Archiving') {
      steps {
        echo ' The Artifact will be uploaded to an artifact repository'
      }
    }
    stage('Testing') {
      steps {
        echo 'The Artifact will be tested'
      }
    }
    stage('Stagging') {
      steps {
        echo 'The Artifact is stagged onto the staging server'
      }
    }

    stage('Deploy') {
      steps {
        echo 'The software will now be deployed !'
      }
    }
  }
}
