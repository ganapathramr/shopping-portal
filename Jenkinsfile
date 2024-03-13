pipeline {
  agent any
  stages {
    stage('build-the-app') {
      steps {
        echo 'this is the build step'
        sh 'npm install'
      }
    }

    stage('test-the-app') {
      steps {
        echo 'this is the test step'
        sh 'npm test'
      }
    }

    stage('package-the-app') {
      steps {
        echo 'this is the third job'
        sh 'npm run package'
      }
    }

    stage('archive') {
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
      echo 'this pipeline has completed...'
    }

  }
}