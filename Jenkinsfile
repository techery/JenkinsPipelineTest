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
      if (currentBuild.result == 'UNSTABLE') {
        currentBuild.result = 'FAILURE'
      }

      throw error
    } finally {
      junit allowEmptyResults: true, testResults: '**/artifacts/test/xunit.xml'
    }

  stage "publish"
    archive (includes: 'src/**')

}
