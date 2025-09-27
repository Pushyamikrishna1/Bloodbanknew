pipeline {
    agent any

    stages {
        stage('Backend Build') {
            steps {
                dir('backend') {
                    // CHANGED: sh to bat
                    bat '.\\mvnw clean package -DskipTests' 
                }
            }
        }

        stage('Frontend Build') {
            steps {
                dir('lifeline-link-22-main') {
                    // CHANGED: sh to bat
                    bat 'npm install'
                    // CHANGED: sh to bat
                    bat 'npm run build'
                }
            }
        }

        stage('Docker Build') {
            steps {
                // CHANGED: sh to bat
                bat 'docker-compose build'
            }
        }
    }
}
