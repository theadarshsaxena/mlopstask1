pipeline {
  agent any
  stages {
    stage('Deploying DevEnv') {
      parallel {
        stage('Deploying DevEnv') {
          steps {
            build 'Job1'
          }
        }

        stage('Testing') {
          steps {
            echo 'Testing the environment automatically (this step can\'t be done because automated testing is out of scope of this post)'
          }
        }

      }
    }

    stage('Approval for Master') {
      steps {
        echo 'is it ok?'
      }
    }

    stage('Deploying in production') {
      parallel {
        stage('Deploying in production') {
          steps {
            build 'job2'
          }
        }

        stage('Sucess') {
          steps {
            echo 'Successfully deployed in the production environment'
          }
        }

      }
    }

  }
}