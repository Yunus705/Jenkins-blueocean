
pipeline {
  agent any
  tools {
        maven 'Maven'
    }
  stages {
    stage('test') {
      steps {
        sh "mvn --version"
      }
    }
    stage('build') {
      steps {
        sh '''pwd
            date'''
      }
    }
    stage('deoloy on test') {
       steps{
        deploy adapters: [
            tomcat9(
                credentialsId: 'testing', 
                path: '', 
                url: 'http://13.201.89.139:8080'
            )
        ], contextPath: '/app', 
        war: '**/*.war'
       }
    }
    stage('deploy on prod') {
      steps {
        deploy adapters: [
            tomcat9(
                credentialsId: 'testing', 
                path: '', 
                url: 'http://13.126.159.208:8080'
            )
        ], contextPath: '/app', 
        war: '**/*.war'
      }
    }
  }
}
