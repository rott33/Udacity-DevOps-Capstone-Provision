pipeline {
	environment {
		awsRegion = 'us-east-2'
		awsCredentials = 'aws-jenkins'
	}
	agent any

	stages {
		stage('Create EKS Cluster') {
			steps {
				withAWS(region:awsRegion, credentials:awsCredentials) {
					sh '''
						eksctl create cluster \
						--name udacity \
						--version 1.14 \
						--nodegroup-name udacity-workers \
						--node-private-networking \
						--node-type t3.medium \
						--nodes 3 \
						--nodes-min 1 \
						--nodes-max 4 \
						--node-ami auto
					'''
				}
			}
		}     
	}
}