pipeline{
	agent any 	
		stages {
			stage('one'){
				steps {
					echo "Hi this is karthik from Trichy"
				}
			}
			stage('two'){
				steps {
					input('Do you want to proceed?')
				}
			}
			stage('three'){
				when {
					not {
						branch 'main'
					}
				}
				steps {
					echo "Hello step 3"
				}
			}
			stage('four') {
				parallel {
					stage('unit test') {
						steps {
							echo 'Running the unit test'
						}
					}
					stage('Integration Test') {
						agent {
							docker {
								reuseNode false
								image 'python:alpine'
								}
							}
				steps {
					echo "Running in integration test ..."
				}
			}	
	}
}
}
}
