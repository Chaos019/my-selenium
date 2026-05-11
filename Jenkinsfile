pipeline {
    agent any
    tools { maven 'Maven' }
    stages {
        stage('Checkout') { steps { checkout scm } }
        stage('Build') { steps { sh 'mvn clean compile' } }
        stage('Test') { steps { sh 'mvn exec:java -Dexec.mainClass="com.example.App"' } }
    }
}
