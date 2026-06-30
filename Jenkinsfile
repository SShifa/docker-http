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
                docker cp index.html q1-2026:/usr/local/apache2/htdocs/index.html
                docker restart q1-2026
                '''
            }
        }
    }
}
