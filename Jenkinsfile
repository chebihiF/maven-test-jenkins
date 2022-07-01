node {
  stage('Git clone') {
    git credentialsId: 'github-private-key', url: 'https://github.com/chebihiF/Spring_boot_app_devops.git'
  }
  stage('Docker build') {
    sh 'docker version'
    sh 'docker build -t tp5_spring_boot_ws .'
    sh 'docker image list'
    sh 'docker tag tp5_spring_boot_ws fhcebihi/tp5_spring_boot_ws'
  }
  stage('Docker login'){
    withCredentials([string(credentialsId: 'DOCKER_HUB_PASSWORD', variable: 'PASSWORD')]) {
        sh 'docker login -u fhcebihi -p $PASSWORD'
    }
  }
  stage("Push Image to Docker Hub"){
    sh 'docker push fhcebihi/tp5_spring_boot_ws'
  }
}
