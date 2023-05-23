pipeline {
	agent any
	//agent
	//docker {
	//	image 'maven:3.6.3'
	//}
	//}
	environment{
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
		
	
	}
	stages{
	stage('Stage Checkout') {
		steps{
		sh 'mvn --version'	
		sh 'docker version'
		echo "Build"
		echo "Build Number is - $env.BUILD_NUMBER"
		echo "$PATH"
		echo "Build Id is - $env.BUILD_ID"
		}
	}
	stage('Build and Complile'){
		steps {
		sh "mvn clean compile"
		}

	}
	stage('Unit Test'){
		steps{
		sh "mvn test"
		}
	
	}
	stage('Integrate Test'){
		steps{
		  sh "mvn failsafe:integration-test failsafe:verify"
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
