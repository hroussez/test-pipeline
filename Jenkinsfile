pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        parallel(
          "Package": {
            sh 'python --version'
            
          },
          "Unit tests": {
            sh 'echo \'unit test\''
            
          },
          "Static Analysis": {
            sh 'echo \'static analysis\''
            
          },
          "Checkmarx": {
            sh 'echo \'checkmarx\''
            
          },
          "JIRA": {
            sh 'echo \'jira\''
            
          }
        )
      }
    }
    stage('Package') {
      steps {
        sh 'echo \'docker\''
        sh 'echo \'rpm\''
      }
    }
  }
}