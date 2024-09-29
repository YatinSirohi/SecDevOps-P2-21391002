pipeline {
  agent {
    docker { image 'node:16-alpine' 
             args '-u root'     //To run as a root               
            }
  }
  stages {
    stage('Install Dependencies') {
      steps {
        sh 'npm install --save'
      }
    }
    stage('Test') {
      steps {
        echo 'Testing...'
        snykSecurity(
          snykInstallation: 'yatin-snyk-api-token',
          snykTokenId: 'acf3db72-60ad-4db0-92b4-caae05429310',
        )
      }
    }
  }
  post {
        success {
            echo 'Pipeline built successfully!'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}
