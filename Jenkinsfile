pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                script {
                    // Assuming 'requirements.txt' is in the root of your project
                    // Adjust the path if your file is located elsewhere
                    dir("${WORKSPACE}") {
                        sh 'pip3 install -r requirements.txt --user'
                    }
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    dir("${WORKSPACE}") {
                        sh 'python -m unittest discover'
                    }
                }
            }
        }

        // Add more stages for deployment if necessary
    }
}
