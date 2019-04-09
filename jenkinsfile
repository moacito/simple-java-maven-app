pipeline {
    agent any
    tools {
      maven 'Maven'
      jdk 'Jdk'
    }
    stages {
      stage('Build') {
        steps {
            sh 'mvn clean package'
        }
      }
      stage('Test') {
        steps {
            sh 'mvn test'
        }
        post {
            always {
                  junit 'target/surefire-reports/*.xml'
            }
         }
      }
   }
}
