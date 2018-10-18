pipeline {
  agent any
  
  stages {
    stage('build') {
      steps {
        sh 'npm config ls'
        sh 'npm install'
        sh 'npm run build'
        sh 'npm test'
      }
    }
    stage('publish') {
      steps {
        archiveArtifacts 'public/**'
      }
    }
  }
}
