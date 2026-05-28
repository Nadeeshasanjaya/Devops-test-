pipeline {
    agent any

    stages {

        stage('Build Maven') {
    steps {
        sh 'chmod +x mvnw'
        sh './mvnw clean package'
    }
}

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t springboot-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 8081:8080 springboot-app'
            }
        }
    }
}