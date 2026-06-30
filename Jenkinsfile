pipeline {
    agent any

    stages {

        stage('Clean Workspace') {
            steps {
                cleanWs()
            }
        }

        stage('Checkout Code') {
            steps {
                checkout scm
            }
        }

        stage('Show Branch & Content') {
            steps {
                sh '''
                echo "Current Branch Build"
                git branch --show-current || true
                cat index.html
                '''
            }
        }

        stage('Deploy Q1') {
            when {
                branch 'q1-2026'
            }
            steps {
                sh '''
                echo "Deploying Q1"
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
                echo "Deploying Q2"
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
                echo "Deploying Q3"
                docker cp index.html q3-2026:/usr/local/apache2/htdocs/index.html
                docker restart q3-2026
                '''
            }
        }
    }
}
