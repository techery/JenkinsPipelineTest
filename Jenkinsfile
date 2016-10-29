#!groovy

node ("nodejs") {
  env.PATH = "/usr/local/bin:${env.PATH}"

  stage "checkout"
    checkout scm

  stage 'npm install'
    sh 'npm install'

  stage 'unit-test'
    sh './node_modules/.bin/jenkins-mocha ./test/*'
    step([$class: 'JUnitResultArchiver', testResults: './artifacts/test/*.xml'])
}
