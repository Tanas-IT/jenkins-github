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
            withDockerRegistry(credentialsId: 'docker-hub', url: 'https://index.docker.io/v1/') {
              sh 'docker build -t tanastestjenkins/helloWorld:v10',
               sh 'docker push -t tanastestjenkins/helloWorld:v10',
            }
         }
      }
   }
}
