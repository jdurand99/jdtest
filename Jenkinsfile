pipeline {
  agent any
  stages {
    stage('error') {
      parallel {
        stage('Build1') {
          steps {
            echo 'Build'
          }
        }
        stage('Build2') {
          steps {
            echo 'Build2'
          }
        }
        stage('Build3') {
          steps {
            echo 'Build3'
          }
        }
      }
    }
    stage('End') {
      steps {
        echo 'End'
      }
    }
  }
  environment {
    Modules = 'mdd1 mdd2'
  }
}