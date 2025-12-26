pipeline {
	agent any
	
	stages {

	stage('Checkout'){
			
	steps {
		git branch: 'main',
		url: 'https://github.com/shelarshriniwas/jenkins-cicd-practice.git'
		    }
			}
	stage('Docker Build'){
		steps {
		
		sh 'docker build -t myapp:v1 .'
		}
	}
	stage('Terraform Init') {
		steps {

		dir('terraform') {
			
			sh 'terraform init'
				}
			}
		}
	stage('Terraform Plan') {
				
		steps {

			dir('terraform'){

				sh 'terraform apply -auto-approve'

				}
			}
		}
					

	}	
}

