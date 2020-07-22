pipeline {
  agent any
  stages {
    stage('Deploying DevEnv') {
      parallel {
        stage('Deploying DevEnv') {
          steps {
            build 'job1'
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
      steps {
        build 'job2'
      }
    }

    stage('Message') {
      steps {
        echo 'successfully deployed everything to the production environment'
      }
    }

  }
}