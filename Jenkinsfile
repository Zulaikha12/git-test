pipeline {
    agent any
    stages {
        stage('Sample') {
                steps {
                        echo 'Hi, this is Zulaikha from edureka'
                }
        }
        stage('Sample2') {
                when {
        	expression {
		steps {
                input('Do you want to proceed?')
                }
		}
		}
        }
        stage('Other branches') {
                when {
                        not {
                                branch "master"
                        }
                }
                steps {
			echo "Hello"
                        }
        }
        stage('Test') {
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

