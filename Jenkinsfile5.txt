pipeline {
    agent any

    stages {
        stage('Input') {
            steps {
                input('Do you want to proceed?')
            }
        }

        stage('If Proceed is clicked') {
            steps {
                print('hello')
            }
        }
    }
}
