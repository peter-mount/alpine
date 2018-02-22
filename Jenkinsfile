imageName = 'area51/alpine'

properties( [
  buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '7', numToKeepStr: '10')),
  disableConcurrentBuilds(),
  disableResume(),
  pipelineTriggers([cron('H H * * *')])
])

node( 'Dev_AMD64_Amsterdam' ) {
  stage( 'Checkout' ) {
    checkout scm
  }

  stage( 'Prepare Build' ) {
    sh 'docker pull area51/alpine:latest'
  }

  stage( 'Build Image' ) {
    sh 'docker build -t ' + imageName + ':latest .'
  }

  stage( 'Publish Image' ) {
    sh 'docker push ' + imageName + ':latest'
  }

}
