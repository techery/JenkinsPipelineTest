#!groovy

env.PATH = "/usr/local/bin:${env.PATH}"

stage 'npm install'
node {
    checkout scm
    sh 'npm install'
}

stage 'unit-test'
node {  
    sh './node_modules/.bin/mocha ./test/*'
}

stage 'hockeyapp'
node {
    echo 'Hello from test'
}
