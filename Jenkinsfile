pipeline{
	agent any
	environment{
		ANYPOINT_CREDS = credentials('ANYPOINT_CREDENTIALS')
	}
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
			environment {
				CLIENT_ID = credentials('DEV_CLIENT_ID')
				CLIENT_SECRET = credentials('DEV_CLIENT_SECRET')
			}
			steps{
				bat 'mvn -B -U -e -V -PDEV deploy -DmuleDeploy -DskipTests -Dusername="%ANYPOINT_CREDS_USR%" -Dpassword="%ANYPOINT_CREDS_PSW%" -Danypoint.platform.client_id="%CLIENT_ID%" -Danypoint.platform.client_secret="%CLIENT_SECRET%"'
			}
		}
	}
}