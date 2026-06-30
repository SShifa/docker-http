[200~pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                checkout scm
            }
        }

        stage('Deploy to Docker HTTPD') {
            steps {
                script {

                    // Q1 branch deployment
                    if (env.BRANCH_NAME == 'q1-2026') {
                        sh '''
                        docker cp index.html q1-2026:/usr/local/apache2/htdocs/index.html
                        docker restart q1-2026
                        '''
                    }

                    // Q2 branch deployment
                    if (env.BRANCH_NAME == 'q2-2026') {
                        sh '''
                        docker cp index.html q2-2026:/usr/local/apache2/htdocs/index.html
                        docker restart q2-2026
                        '''
                    }

                    // Q3 branch deployment
                    if (env.BRANCH_NAME == 'q3-2026') {
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
