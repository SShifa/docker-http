pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Deploy Q1') {
            steps {
                sh '''
                git checkout q1-2026
                docker cp index.html q1-2026:/usr/local/apache2/htdocs/index.html
                '''
            }
        }

        stage('Deploy Q2') {
            steps {
                sh '''
                git checkout q2-2026
                docker cp index.html q2-2026:/usr/local/apache2/htdocs/index.html
                '''
            }
        }

        stage('Deploy Q3') {
            steps {
                sh '''
                git checkout q3-2026
                docker cp index.html q3-2026:/usr/local/apache2/htdocs/index.html
                '''
            }
        }
    }
}
