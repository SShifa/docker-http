pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Deploy Q2') {
            steps {
                sh '''
                docker cp index.html q2-2026:/usr/local/apache2/htdocs/index.html
                docker restart q2-2026
                '''
            }
        }
    }
}
