pipeline{
	agent any
	
	stages{
		stage('Build'){
			steps{
				bat 'mvn clean install'
			}
		}
		stage('Test'){
			steps{
				bat 'mvn test'
			}
		}
		stage(‘Deployment’){
			environment{
				ENVIRONMENT = 'DEV'
				APP_NAME = ''
			}
			steps{
				bat 'mvn deploy -DmuleDeploy'
			}
		}
	}
}