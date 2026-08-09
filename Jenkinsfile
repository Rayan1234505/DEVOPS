pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/Rayan1234505/DEVOPS.git'
            }
        }

        stage('Check Java and Maven') {
            steps {
                sh '''
                    java -version
                    mvn -version
                '''
            }
        }

        stage('Build with Maven') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Run Tests') {
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
            echo 'Maven build failed!'
        }
    }
}
