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
            sh 'echo RPM'
            
          }
        )
      }
    }
    stage('Security Scan') {
      steps {
        parallel(
          "BD Docker": {
            sh 'echo \'docker\''
            
          },
          "BD RPM": {
            sh 'echo RPM'
            
          }
        )
      }
    }
    stage('Publish') {
      steps {
        parallel(
          "Docker": {
            sh 'echo \'docker\''
            
          },
          "RPM": {
            sh 'echo RPM'
            
          }
        )
      }
    }
    stage('Stage deploy') {
      steps {
        sh 'echo \'deploy stage\''
      }
    }
    stage('Stage load test') {
      steps {
        sh 'echo \'stage load test\''
      }
    }
    stage('Stage regression test') {
      steps {
        sh 'echo \'stage regression test\''
      }
    }
    stage('Promote to production') {
      steps {
        sh 'echo \'promote to production\''
      }
    }
    stage('Deploy to production') {
      steps {
        sh 'echo \'deploy to production\''
      }
    }
  }
}
