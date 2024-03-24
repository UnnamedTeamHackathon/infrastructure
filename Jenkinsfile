pipeline {
    agent any
    options {
        ansiColor('xterm')
        timestamps()
        disableConcurrentBuilds()
        timeout(time: 1, unit: 'HOURS') 
        buildDiscarder(logRotator(artifactDaysToKeepStr: '7', artifactNumToKeepStr: '10', daysToKeepStr: '7', numToKeepStr: '50'))
    }
    stages {
        stage('verify tooling') {
            sh '''
                docker version
                docker info
                docker compose version
                curl --version
            '''
        }
    }
}