pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo 'this is the first job'
        sh 'npm install'
        sleep 4
      }
    }

    stage('test') {
      steps {
        echo 'this is the second job'
        sh 'npm test'
        sleep 9
      }
    }

    stage('package') {
      steps {
        echo 'this is the third job'
        sh 'npm run package'
        archiveArtifacts '**distribution/*.zip'
      }
    }

  }
  tools {
    nodejs 'NodeJS 20.19.1'
  }
  post {
    always {
      echo 'this pipeline has completed...'
    }

  }
}