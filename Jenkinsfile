pipeline {
    agent any

    stages {

        stage('Deploy Q1') {
            when {
                branch 'q1-2026'
            }
            steps {
                sh '''
                git checkout q1-2026
                docker cp index.html q1-2026:/usr/local/apache2/htdocs/index.html
                docker restart q1-2026
                '''
            }
        }

        stage('Deploy Q2') {
            when {
                branch 'q2-2026'
            }
            steps {
                sh '''
                git checkout q2-2026
                docker cp index.html q2-2026:/usr/local/apache2/htdocs/index.html
                docker restart q2-2026
                '''
            }
        }

        stage('Deploy Q3') {
            when {
                branch 'q3-2026'
            }
            steps {
                sh '''
                git checkout q3-2026
                docker cp index.html q3-2026:/usr/local/apache2/htdocs/index.html
                docker restart q3-2026
                '''
            }
        }
    }
}
