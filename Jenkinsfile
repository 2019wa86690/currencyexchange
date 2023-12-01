pipeline{
	//agent any
	agent any 
	stages{
		stage('Build'){
			steps{
				echo "Build"
				echo "$PATH"
				echo "Build number - $env.BUILD_NUMBER"
				echo "$env.BUILD_ID"
				echo "$env.BUILD_TAG"
				echo "$env.BUILD_URL"
				//sh 'mvn --version'
			}
		}
		stage('Test'){
			steps{
				echo "Test"
			}
		}
		stage('Integrate'){
			steps{
				echo "Integrate"
			}
		}
	}
	post{
		always {
			echo "I am Awesome. I run always"
		}
		success{
			echo "I run when all are successful"
		}
		failure {
			echo "I run when you fail"
		}
	}
}
			
