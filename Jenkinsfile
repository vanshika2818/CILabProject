pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                // Example for Maven
                sh './scripts/build.sh' 
            }
        }
        stage('Test') {
            steps {
                echo 'Running Unit Tests...'
                // Run your CalculatorTest.java here
            }
        }
        stage('Deploy') {
            steps {
                sh './scripts/deploy.sh'
            }
        }
    }
}