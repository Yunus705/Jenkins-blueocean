pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh '''pwd
            date'''
      }
    }

    stage('test') {
      parallel {
        stage('test') {
          steps {
            echo 'test step'
          }
        }

        stage('test para') {
          steps {
            echo 'test para'
          }
        }

      }
    }

    stage('deploy') {
      steps {
        echo 'deploy'
      }
    }

  }
}