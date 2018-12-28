pipeline {
  agent any
  parameters {
    string(defaultValue: "TEST", description: 'What environment?', name: 'userFlag')
    choice(choices: ['US-EAST-1', 'US-WEST-2'], description: 'What AWS region?', name: 'region')
  }
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