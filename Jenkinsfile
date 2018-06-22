pipeline {
    agent {
        docker { image 'hello-world' }
    }
    stages {
        stage('Test') {
            steps {
                sh 'node --version'
            }
        }
    }
}
