pipeline {
    agent any

    tools {
        maven 'M3'
    }

    stages {

        stage('Check Java and Maven') {
            steps {
                bat '''
                    java -version
                    mvn -version
                '''
            }
        }

        stage('Build with Maven') {
            steps {
                bat 'mvn clean package'
            }
        }

        stage('Run Tests') {
            steps {
                bat 'mvn test'
            }
        }
    }

    post {
        success {
            echo 'Maven build completed successfully!'
        }

        failure {
            echo 'Maven build failed!'
        }
    }
}
