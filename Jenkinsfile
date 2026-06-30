pipeline {
    agent any

    stages {

        stage('Clean Workspace') {
            steps {
                cleanWs()
            }
        }

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Detect Branch') {
            steps {
                script {
                    env.BRANCH = sh(
                        script: "git rev-parse --abbrev-ref HEAD || echo detached",
                        returnStdout: true
                    ).trim()

                    echo "Branch detected: ${env.BRANCH}"
                }
            }
        }

        stage('Deploy Q1') {
            when {
                expression { env.BRANCH.contains('q1') }
            }
            steps {
                sh '''
                docker cp index.html q1-2026:/usr/local/apache2/htdocs/index.html
                docker restart q1-2026
                '''
            }
        }

        stage('Deploy Q2') {
            when {
                expression { env.BRANCH.contains('q2') }
            }
            steps {
                sh '''
                docker cp index.html q2-2026:/usr/local/apache2/htdocs/index.html
                docker restart q2-2026
                '''
            }
        }

        stage('Deploy Q3') {
            when {
                expression { env.BRANCH.contains('q3') }
            }
            steps {
                sh '''
                docker cp index.html q3-2026:/usr/local/apache2/htdocs/index.html
                docker restart q3-2026
                '''
            }
        }
    }
}
