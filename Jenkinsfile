pipeline {
  agent any
  parameters {
    booleanParam(defaultValue: true, description: 'repo1?', name: 'repo1')
    booleanParam(defaultValue: true, description: 'repo2?', name: 'repo2')
    booleanParam(defaultValue: true, description: 'checkout?', name: 'checkout')
  }
  stages {
    stage("foo") {
      steps {
        echo "Repo1: ${params.repo1}"
        echo "Repo2: ${params.repo2}"
      }
    }
    stage('Checkout') {
      when {
        expression {
          return ${params.checkout}
        }
      }
      steps {
        script {
          repolist = []
          repolist += "https://github.com/jdurand99/repo1.git"
          repolist += "https://github.com/jdurand99/repo2.git"
          
          for (def element = 0; element < repolist.size(); element++) {
                echo repolist[element]
                git credentialsId: 'github', url: repolist[element]
          }
        }
      }
    }   
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
      parallel {
        stage('Build boucle') {
          steps {
            script {
              MYLIST = []
              MYLIST += "param-one"
              MYLIST += "param-two"
              MYLIST += "param-three"
              MYLIST += "param-four"
              MYLIST += "param-five"

              for (def element = 0; element < MYLIST.size(); element++) {
                echo MYLIST[element]
              }
            }

          }
        }
        stage('script toto') {
          steps {
            script {
              echo 'toto'
            }

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
}