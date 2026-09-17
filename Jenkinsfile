pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/ratakondadimpul/agile_17_6.git'
            }
        }

        stage('Build') {
            steps {
                sh 'python3 -m py_compile app.py'
                echo 'Build successful: app.py compiled with no syntax errors'
            }
        }

        stage('Send Notification') {
            steps {
                mail to: 'ratakondadimpul2628@gmail.com, ratakonda.dimpul2024@vitstudent.ac.in',
                     subject: "Build Notification: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                     body: """The Jenkins build has completed successfully.

Job: ${env.JOB_NAME}
Build Number: ${env.BUILD_NUMBER}
Build URL: ${env.BUILD_URL}
"""
            }
        }
    }
}