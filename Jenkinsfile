#!groovy

env.PATH = "/usr/local/bin:${env.PATH}"

node ("nodejs") {
  stage "checkout"
    checkout scm

  stage 'npm install'
    sh 'npm install'

  stage 'unit-test'
    sh './node_modules/.bin/mocha ./test/*'
}
