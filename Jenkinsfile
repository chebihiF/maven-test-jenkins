pipeline {
    agent any
    stages {
      stage('Git clone') {
        git credentialsId: 'github-private-key', url: 'https://github.com/chebihiF/tp5_spring_boot_ws.git'
      }
      stage('Docker build') {
        sh 'docker version'
        sh 'docker build -t tp5_spring_boot_ws .'
        sh 'docker image list'
        sh 'docker tag tp5_spring_boot_ws fhcebihi/tp5_spring_boot_ws:1.0'
      }
    }
}
