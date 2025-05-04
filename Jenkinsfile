pipeline {
    agent any

    tools {
        maven 'MAVEN_HOME'
        jdk 'JDK8'
    }

    stages {
        stage('Checkout Code') {
            steps {
                git 'https://github.com/Madhanzz/1CD22CS171_jenkins.git'
            }
        }
        stage('Build') {
            steps {
                echo 'Building the project...'
                bat 'mvn clean install'
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
                echo 'Packaging the app...'
                bat 'mvn package'
            }
        }
        stage('Deploy (Optional)') {
            steps {
                echo 'Deploy step (can be configured later)...'
            }
        }
    }

    post {
        success {
            echo '✅ Build and tests SUCCESS!'
        }
        failure {
            echo '❌ Build FAILED. Check errors in console.'
        }
    }
}
