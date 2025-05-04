pipeline {
    agent any

    tools {
        maven 'MAVEN_HOME' // Make sure this matches the Maven name configured in Jenkins ➔ Manage Jenkins ➔ Global Tool Configuration
    }

    stages {
        stage('Build') {
            steps {
                bat 'mvn clean install -B' // -B (batch mode) ➔ better for CI logs
            }
        }
    }
}
