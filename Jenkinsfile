properties([pipelineTriggers([githubPush()])])

node('linux') {
    git url: 'https://github.com/lesherd/infrastructure-pipeline.git', branch: 'master'
    stage('Test') {
        sh "env"
    }
}        
