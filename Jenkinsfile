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
      post {
        success {
          stash includes: "public/**", name: "web-public"
        }
      }
    }
    stage('publish') {
      steps {
        unstash "web-public"
        archiveArtifacts 'public/**'
        sshPublisher(publishers: [sshPublisherDesc(configName: 'myserver', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '', remoteDirectorySDF: false, removePrefix: 'public', sourceFiles: 'public/**')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
      }
    }
    stage('integration test') {
      steps {
        sh 'curl www.google.ca'
      }
      step([$class: 'hudson.plugins.chucknorris.CordellWalkerRecorder']) {
      }
    }
  }
}
