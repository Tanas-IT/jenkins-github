pipeline {
   agent any
   stages {
      stage('Clone') {
         steps {
            git branch: 'main', url: 'https://github.com/Tanas-IT/jenkins-github.git'
         }
      }
      stage('Build') {
         steps{
            withDockerRegistry(credentialsId: 'docker-hub', url: 'https://hub.docker.com/') {
              sh 'docker build -t tanas942/testjenkin .'
               sh ' docker push tanas942/testjenkin'
            }
         }
      }
   }
}
