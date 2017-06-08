pipeline {
  agent any
  stages {
    stage('Build & Test') {
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
            
          },
          "roman": {
            sh 'echo hello'
            
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
      when {
        branch 'master'
      }
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
    stage('Stage') {
      when {
        branch 'master'
      }
      steps {
        sh 'echo \'deploy stage\''
        sh 'echo \'stage load test\''
        sh 'echo \'stage regression test\''
      }
    }
    stage('Promote') {
      when {
        branch 'master'
      }
      steps {
        timeout(time: 1, unit: 'HOURS') {
          input 'Deploy to Production?'
        }
        
        sh 'echo \'promote to production\''
      }
    }
    stage('Deploy to production') {
      when {
        branch 'master'
      }
      steps {
        sh 'echo \'deploy to production\''
      }
    }
  }
}