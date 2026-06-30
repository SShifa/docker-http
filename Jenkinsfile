pipeline {
    agent any

    stages {

        stage('Clean') {
            steps {
                cleanWs()
            }
        }

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Deploy') {
            steps {
                script {

                    def branch = sh(script: "git rev-parse --abbrev-ref HEAD || echo detached", returnStdout: true).trim()

                    if (branch.contains("q1")) {
                        sh '''
                        docker cp index.html q1-2026:/usr/local/apache2/htdocs/index.html
                        docker restart q1-2026
                        '''
                    }

                    if (branch.contains("q2")) {
                        sh '''
                        docker cp index.html q2-2026:/usr/local/apache2/htdocs/index.html
                        docker restart q2-2026
                        '''
                    }

                    if (branch.contains("q3")) {
                        sh '''
                        docker cp index.html q3-2026:/usr/local/apache2/htdocs/index.html
                        docker restart q3-2026
                        '''
                    }
                }
            }
        }
    }
}
