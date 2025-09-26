pipeline {
    agent any

    stages {
        stage('Backend Build') {
            steps {
                dir('backend') {
                    sh './mvnw clean package -DskipTests'
                }
            }
        }

        stage('Frontend Build') {
            steps {
                dir('lifeline-link-22-main') {
                    sh 'npm install'
                    sh 'npm run build'
                }
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker-compose build'
            }
        }
    }
}
