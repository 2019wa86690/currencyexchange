pipeline{
	//agent any
	agent { docker { image 'node:13.8'} } 
	stages{
		stage('Build'){
			steps{
				echo "Build"
				sh 'node --version'
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
			
