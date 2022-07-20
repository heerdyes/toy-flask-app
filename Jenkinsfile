pipeline {
  agent { docker { image 'python:3.9.9' } }
  stages {
    stage('build') {
      steps {
        sh 'pip install --target ${env.WORKSPACE} -r requirements.txt'
      }
    }
    stage('test') {
      steps {
        sh 'python test.py'
      }
      post {
        always {
          junit 'test-reports/*.xml'
        }
      }
    }
  }
}

