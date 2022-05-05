pipeline {
  agent any
  
  options {
    buildDiscarder logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')
    disableConcurrentBuilds()
  }
  stages {
    stage('Hello') {
      steps {
        echo "hello, this is a change"
      }
    }
    
    stage ('Cat README') {
      when {
        branch "fix-*"  // this stage will be executed only for the branches
      }                 // matching this pattern
      steps {
        sh '''
  	      cat README.md
  	    '''
      }
    }
  }
}
