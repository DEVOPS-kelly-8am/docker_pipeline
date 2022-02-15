pipeline {
  agent any
  stages {

    stage('checkout SCM') {
      steps {
        script {
          echo 'checkout SCM'
        }
      }
    }

    stage('Build') {
      steps {
        script {
          sh 'mvn clean install'
        }
      }
    }
    stage('test') {
      steps {
        script {
          sh 'mvn clean test'
        }
      }
    }
  }
}