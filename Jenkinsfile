node{
  def myImg
    stage ('Build image') {
        // download the dockerfile to build from
          checkout scm
        // build our docker image
        myImg = docker.build 'my-image:nginx'
    }
    stage ('Run') {
      
      docker.image('my-image:nginx').withRun('-p 80:80') { c ->
      sh 'docker ps'
      sh 'curl localhost'
    }
    }
}
