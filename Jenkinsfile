#!groovy

node ("nodejs") {
  env.PATH = "/usr/local/bin:${env.PATH}"

  stage "checkout"
    checkout scm

  stage 'npm install'
    sh 'npm install'

  stage 'unit-test'
    try {
      sh './node_modules/.bin/jenkins-mocha ./test/*'
    } catch(error) {
      step([$class: 'JUnitResultArchiver', testResults: '**/artifacts/test/xunit.xml'])
      // if (currentBuild.result == 'UNSTABLE') {
      //   currentBuild.result = 'FAILURE'
      // }
      //
      // throw error
    }

  stage "publish"
     archive (includes: 'pkg/*.gem')

}
