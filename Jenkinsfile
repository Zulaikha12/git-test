pipeline {
    agent any
    stages {
        stage('Sample') {
                steps {
                        echo 'Hi, this is Zulaikha from edureka'
                }
        }
        stage('Master branch') {
                when {
                        branch "master"
                
                steps {
                        echo "This is the master branch"
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
                        agent any
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

