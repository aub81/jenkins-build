node() {
    def myImg
    stage ("Build image") {
        // download the dockerfile to build from
        git https://github.com/aub81/jenkins-build.git

        // build our docker image
        myImg = docker.build 'my-image:nginx'
    }
    stage ("Run") {
      
      docker.image('my-image:ngin').withRun('-p 80:80') { c ->
      sh 'docker ps'
      sh 'curl localhost'
    }
}
