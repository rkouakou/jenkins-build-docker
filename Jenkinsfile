


node{
  def app

    stage('Clone') {
        checkout scm
    }

    stage('Build image') {
        app = docker.build("roland/nginx")
    }

    stage('Test image') {
        docker.image('roland/nginx').withRun('-p 80:80') { c ->
        sh 'docker ps'
        sh 'curl localhost'
	     }
    }
}

