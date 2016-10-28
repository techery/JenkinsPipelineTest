#!groovy

stage 'npm install'
node {
    env.PATH = "/usr/local/bin:${env.PATH}"    
    sh 'npm install'
}

stage 'build'
node {
    echo 'project build'
}

stage 'unit-test'
node {
    echo 'Hello from test'
}

stage 'smoke-test'
node {
    echo 'Hello from test'
}

stage 'hockeyapp'
node {
    echo 'Hello from test'
}
