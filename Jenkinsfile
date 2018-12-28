pipeline {

  abcs = ['a', 'b', 'c']

  def loop(list) {
    for (i in [list]) {
      echo i
   }
  }
  
  agent any
  stages {
    stage('Build') {
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
    stage('Build boucle') {
      loop(abc)         
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

