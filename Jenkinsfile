pipeline {

 
  
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
  }
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

