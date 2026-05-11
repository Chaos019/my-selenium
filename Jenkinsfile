pipeline {
    agent any

    tools {
        maven 'maven'
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/chinmayiii/mavenselenium.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Run Selenium') {
            steps {
                sh 'mvn exec:java -Dexec.mainClass="com.example.App"'
            }
        }
    }

    post {

        success {
            echo 'Login Successful'
            echo 'Open SauceDemo Inventory Page: https://www.saucedemo.com/inventory.html'
        }

        failure {
            echo 'Build FAILED'
        }
    }
}
