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
           sshPublisher(publishers: [sshPublisherDesc(configName: 'my-remote-server', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: 'cp index.html index-demo.html', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '', remoteDirectorySDF: false, removePrefix: '', sourceFiles: 'index.html')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
         }
      }
   }
}
