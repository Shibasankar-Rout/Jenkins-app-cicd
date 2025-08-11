pipeline {
  agent any

  tools {

    nodejs 'NodeJS_14'
  }  



  stages {
    stage('Checkout') {
      steps { checkout scm }

    }
    
    stage('Install') { 
      steps { sh 'npm install' }

    }

    stage('Test') {
      steps { sh 'npm test' }
      post {
        always { junit 'test-results/results.xml' }
      }
    }
  } 

 
 post {
    success { echo 'Pipeline succeeded' }
    failure { echo 'Pipeline failed' }

  }
}