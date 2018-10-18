pipeline {
  agent any
  
  stages {
    stage('build') {
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
