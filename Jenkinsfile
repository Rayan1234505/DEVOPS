pipeline {
    agent any

    tools {
        jdk 'JDK'
        maven 'Maven'
    }

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/Rayan1234505/DEVOPS.git'
            }
        }

        stage('Check Files') {
            steps {
                sh 'ls -la'
                sh 'java -version'
                sh 'mvn -version'
            }
        }

        stage('Build with Maven') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Run Test') {
            steps {
                sh 'mvn test'
            }
        }
    }

    post {
        success {
            echo 'Maven build completed successfully!'
        }
        failure {
            echo 'Maven build failed.'
        }
    }
}
