#!groovy

env.PATH = "/usr/local/bin:${env.PATH}"

stage 'npm install' {
  node {
      checkout scm
      sh 'npm install'
  }
}


stage 'unit-test' {
  node {
      sh 'npm test'
  }
}

stage 'hockeyapp' {
  node {
      echo 'Hello from test'
  }
}
