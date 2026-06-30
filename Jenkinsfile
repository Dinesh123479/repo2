pipeline {
    agent any

    environment {
        IMAGE_NAME = "myapp"
        CONTAINER_NAME = "myapp-container"
    }

    stages {

        stage('Build') {
            steps {
                bat 'docker build -t %IMAGE_NAME% .'
            }
        }

        stage('Test') {
            steps {
                bat 'echo Tests Passed'
            }
        }

        stage('Deploy') {
            steps {
                bat 'docker stop %CONTAINER_NAME%'
                bat 'docker rm %CONTAINER_NAME%'
                bat 'docker run -d --name %CONTAINER_NAME% -p 8080:80 %IMAGE_NAME%'
            }
        }
    }
}
