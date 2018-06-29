pipeline {
    agent any
    stages {
        stage('Sample') {
                steps {
                        echo 'Hi, this is Zulaikha from edureka'
                }
        }
	    stage('User input'){
		    
		steps {
			input('Do you want to proceed?')
        }
	    }
        stage('when directive') {
                when {
                        not {
                                branch "master"
                        }
                }
                steps {
			echo "Hello"
                        }
        }
        stage('parallel directive') {
                parallel {
                        stage('Unit Test') {
                                steps{
                                        echo "Running the unit test..."
                                }
                        }
                        stage('Integration test') {
                        agent {
                                docker {
                                        reuseNode true
			image 'ubuntu'
                                        }
                                }
				steps {
					sh "ls"
				}
				
                        }
                }
        }
    }
}

