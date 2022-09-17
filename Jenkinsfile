pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        bat 'mvn clean package'
      }
    }

    stage('install packae') {
      parallel {
        stage('install packae') {
          steps {
            bat 'mvn install'
          }
        }

        stage('deploy') {
          steps {
            bat 'mvn sonar:sonar'
          }
        }

      }
    }

    stage('deploy') {
      steps {
        bat 'mvn deploy'
      }
    }

    stage('') {
      steps {
        slackSend()
      }
    }

  }
}