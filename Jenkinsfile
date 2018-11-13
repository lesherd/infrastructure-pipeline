properties([pipelineTriggers([githubPush()])])

node('linux') {
    git url: 'https://github.com/lesherd/infrastructure-pipeline.git', branch: 'master'
    stage('Test') {
        sh "aws ec2 describe-instances --region us-east-1"
    }
    stage('GetInstances') {    
		  
	}   
	stage('CreateInstance') {    
		//TODO  
	}
    
}        
