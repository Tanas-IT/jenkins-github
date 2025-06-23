pipeline {
   agent any
   stages {
      stage('Clone') {
         steps {
            git branch: 'main', url: 'https://github.com/Tanas-IT/jenkins-github.git'
         }
      }
      // stage('Build') {
      //    steps{
      //       withDockerRegistry(credentialsId: 'user-docker', url: 'https://index.docker.io/v1/') {
      //         sh 'docker build -t tanas942/testdeployjenkin:0.0.1 .'
      //          sh 'docker push tanas942/testdeployjenkin:0.0.1'
      //       }
      //    }
      // }
      stage('SSH server') {
         steps {
            sshagent(['deploy-dev']) {
               sh 'ssh -o StrictHostKeyChecking=no -l cloudbees 192.168.1.106 touch test.txt'
            }
         }
      }
   }
}
