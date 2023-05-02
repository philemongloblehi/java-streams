pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'mvn clean install'
      }
    }

    stage('Tests') {
      parallel {
        stage('Unit') {
          steps {
            sh 'mvn test'
          }
        }

        stage('Integration') {
          steps {
            sh 'mvn test'
          }
        }

        stage('Functional') {
          steps {
            sh 'mvn test'
          }
        }

      }
    }

    stage('Deployment') {
      steps {
        sh 'mvn package'
      }
    }

  }
}