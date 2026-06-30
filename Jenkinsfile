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

        stage('Show Git Content') {
            steps {
                sh 'echo "Branch:" && git branch --show-current'
                sh 'cat index.html'
            }
        }

        stage('Deploy') {
            steps {
                script {

                    def branch = sh(script: "git branch --show-current", returnStdout: true).trim()

                    if (branch == "q1-2026") {
                        sh '''
                        docker cp index.html q1-2026:/usr/local/apache2/htdocs/index.html
                        docker restart q1-2026
                        '''
                    }

                    if (branch == "q2-2026") {
                        sh '''
                        docker cp index.html q2-2026:/usr/local/apache2/htdocs/index.html
                        docker restart q2-2026
                        '''
                    }

                    if (branch == "q3-2026") {
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
