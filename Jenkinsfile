pipeline{
	agent any
	
	stages{
		stage('Build'){
			steps{
				bat 'mvn -B -U -e -V clean install -DskipTests'
			}
		}
		stage('Test'){
			steps{
				bat 'mvn test'
			}
		}
		stage(‘Deployment’){
		
			steps{
				bat 'mvn -B -U -e -V deploy -DmuleDeploy -DskipTests'
			}
		}
	}
}