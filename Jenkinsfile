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
				echo "***** MUnit test cases execution *****"
			}
		}
		stage(‘Deployment’){
		
			steps{
				bat 'mvn -B -U -e -V -Pdev deploy -DmuleDeploy -DskipTests'
			}
		}
	}
}