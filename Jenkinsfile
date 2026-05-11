pipeline {
    agent any

    tools {
        maven 'Maven'
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                url: 'https://github.com/Chaos019/my-selenium.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Run Selenium') {
            steps {
                sh 'mvn exec:java'
            }
        }
    }

    post {
        success {
            echo "Open SauceDemo: https://www.saucedemo.com"
        }

        failure {
            echo "Build FAILED"
        }
    }
}
