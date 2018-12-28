pipeline {
  agent any
  stages {
    stage('') {
      steps {
        echo 'Build'
      }
    }
    stage('End') {
      steps {
        mail(subject: 'End', body: 'test', to: 'jerome.durand99@free.fr')
      }
    }
  }
  environment {
    Modules = 'mdd1 mdd2'
  }
}