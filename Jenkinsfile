pipeline{
	//agent any
	agent any 
	stages{
		stage('Build'){
			steps{
				echo "Build"
				sh "mvn --version"
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
			
