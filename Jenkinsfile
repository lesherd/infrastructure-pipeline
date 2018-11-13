properties([pipelineTriggers([githubPush()])])

node('linux') {
    git url: 'https://github.com/lesherd/infrastructure-pipeline.git', branch: 'master'
    stage('Test') {
        sh "env"
    }
    stage('GetInstances') {    
	sh "aws ec2 describe-instances --region us-east-1"	  
    }   
    stage('CreateInstance') {    
        sh "aws ec2 run-instances --image-id ami-013be31976ca2c322 --count 1 --instance-type t2.micro --key-name testKey1 --security-group-ids sg-82175ece --subnet-id subnet-cccf4c90 --region us-east-1"
    }
    stage('DescribeInstance') {	
	sh "aws ec2 describe-instances | jq '[.Reservations | .[] | .Instances | .[] | {InstanceId: .InstanceId, State: .State, SubnetId: .SubnetId, VpcId: .VpcId, Name: (.Tags[]|select(.Key==\"Name\")|.Value)}]'"
    }	    
    
}        
