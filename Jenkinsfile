pipeline{
	//agent any
	agent any 
	environment{
		dockerHome = tool 'docker'
		mavenHome = tool 'Maven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages{
		stage('Checkout'){
			steps{
				sh 'mvn --version'
				sh 'docker --version'
				echo "Build number - $env.BUILD_NUMBER"
				echo "$env.BUILD_ID"
				echo "$env.BUILD_TAG"
				echo "$env.BUILD_URL"
				//sh 'mvn --version'
			}
		}
		stage ('Build'){
			steps{
				sh "mvn clean compile"
			}
		}
		stage('Test'){
			steps{
				sh "mvn test"
			}
		}
		stage('Package'){
			steps{
				sh "mvn package -DskipTests"}
		}
		stage (' Build Docker Image'){
			steps{
				//docker build -t in28min/currency-exchange-devops:$env.BUILD_TAG
				script{
					dockerImage = docker.build("ankushvk22/currency-exchange-devops:${env.BUILD_TAG}")
				}
			}
		}
		stage ('Push Docker Image'){
			steps{
			    script{
				    docker.withRegistry('','dockerhub'){
				    dockerImage.push();
				    dockerImage.push('latest');
				    }
			    }
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
			
