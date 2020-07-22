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

    stage('Deployment to production system') {
      input {
                message "Should we continue?"
                ok "Yes, we should."
                submitter "adarsh"
                parameters {
                    string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
                           }
       }
      steps {
        echo "Called by: ${params.name}"
        sh 'echo "deployment to production system started"'
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
