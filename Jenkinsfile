pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        parallel(
          "Compile": {
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
        parallel(
          "Docker": {
            sh 'echo \'docker\''
            
          },
          "RPM": {
            sh 'RPM'
            
          }
        )
      }
    }
    stage('Publish') {
      steps {
        sh 'echo \'publish\''
      }
    }
  }
}