pipeline {
  agent any
  
  stages {
    stage('deploy') {
      steps {
        sh 'npm config ls'
        echo 'installing npm...'
        sh 'npm install'
        sh 'npm run build'
        sh 'npm test'
      }
    }
  }
}
