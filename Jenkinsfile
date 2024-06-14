pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Build Completed'
        retry(count: 3) {
          echo 'trying Build'
        }

      }
    }

    stage('Test') {
      parallel {
        stage('Test2') {
          steps {
            echo 'Running test2'
          }
        }

        stage('Test1') {
          steps {
            echo 'Running Test1'
          }
        }

      }
    }

    stage('deploy') {
      steps {
        input(message: 'Are u sure to deploy?', ok: 'yes, i\'m sure!!')
        echo 'deploy completed'
      }
    }

    stage('Notify for new build') {
      steps {
        echo 'New build completed'
      }
    }

  }
}