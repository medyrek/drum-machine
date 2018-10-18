pipeline {
  agent any
 
  tools {nodejs "node"}
 
  stages {
    stage('deploy') {
      steps {
        sh 'npm config ls'
        sh 'npm install'
        sh 'npm run build'
        sh 'npm test'
      }
    }
  }
}
