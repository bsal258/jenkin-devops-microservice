pipeline {
	//agent any
	agent{
	docker {
		image 'maven:3.6.3'
	}
	}
	stages{
	stage('Build') {
		steps{
		//sh 'mvn --version'
		echo "Build"
		echo "Build Number is - $env.BUILD_NUMBER"
		echo "$PATH"
		echo "Build Id is - $env.BUILD_ID"
		}
	}
	stage('Test') {
		steps{
		echo "Test"
	}
	}
	stage('Integration Test'){
		steps{
		echo 'Integration Test'
	}
	}
	}
	post{
	  always{
		echo 'awesome'
	   }
	  success {
		echo 'this is a sucess'
	}
	failure{
		echo 'this failed'
	}
	}
}
