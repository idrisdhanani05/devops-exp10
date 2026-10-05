pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out source code from GitHub...'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the Maven project...'
                bat 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                echo 'Running unit tests...'
                bat 'mvn test'
            }
        }

        stage('Package') {
            steps {
                echo 'Packaging the application...'
                bat 'mvn package -DskipTests'
            }
        }
    }

    post {
        success {
            echo 'DEVOPS PIPELINE EXECUTED SUCCESSFULLY!'
        }

        failure {
            echo 'PIPELINE FAILED. CHECK THE CONSOLE OUTPUT.'
        }
    }
}