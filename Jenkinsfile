pipeline {
  agent any
  stages {
    stage('Install') {
      steps { bat 'npm install' }
    }
 
    stage('Test') {
      parallel {
        stage('Static code analysis') {
            steps { bat 'npm run lint' }
        }
        stage('Unit tests') {
            steps { bat 'npm run test' }
        }
      }
    }
 
    stage('Build') {
      steps { bat 'npm run build' }
    }
  }
}