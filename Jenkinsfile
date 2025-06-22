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
            withDockerRegistry(credentialsId: '8af7fbd4-0c9f-4361-b834-c9235d3a1033', url: 'https://index.docker.io/v1/') {
              sh 'docker build -t tanas942/testdeployjenkin:0.0.1 .'
               sh 'docker push tanas942/testdeployjenkin:0.0.1'
            }
         }
      }
   }
}
