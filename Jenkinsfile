pipeline {
	agent any
	stages{
	stage('Build') {
		steps{
		echo "Build"
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
