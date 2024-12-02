node {
  stage('Clone repository') {
    git credentialsId: 'Jenkins_Private_Key', url: 'https://github.com/highsky1/jenkins-study-web-count.git'
  }

  stage('Build image') {
    dockerImage = docker.build("highsky1/web_count:v1.0")
  }

  stage('Push image') {
    withDockerRegistry([ credentialsId: "docker_access_token", url: "" ]) {
    dockerImage.push()
    }
  }
}
