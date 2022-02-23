pipeline {
  agent any
  stages {
    stage('shopping-portal-compile-app') {
      steps {
        echo 'this is to compile shopping portal app'
        sh 'npm install'
        sleep 2
      }
    }

    stage('shopping-portal-run-tests') {
      steps {
        echo 'this is to run the shopping portal tests'
        sh 'npm test'
        sleep 2
      }
    }

    stage('shopping-portal-package-app') {
      steps {
        echo 'this is to package shopping portal app'
        sh 'npm run package'
        sleep 2
      }
    }

    stage('shopping-portal-archive') {
      steps {
        archiveArtifacts '**/distribution/*.zip'
      }
    }

  }
  tools {
    nodejs 'nodejs'
  }
  post {
    always {
      echo 'shopping portal pipeline has completed...'
    }

  }
}