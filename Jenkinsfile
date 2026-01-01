pipeline {
    agent any

    stages {

        stage('Clone Code from GitHub') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/viren-ladkat24/1stjenkinsproject.git'
            }
        }

        stage('Deploy Static Website') {
            steps {
                sh '''
                echo "Cleaning old website files"
                sudo rm -rf /var/www/html/*

                echo "Deploying new files"
                sudo cp -r * /var/www/html/
                '''
            }
        }
    }

    post {
        success {
            echo "✅ Website deployed successfully"
        }
        failure {
            echo "❌ Deployment failed"
        }
    }
}
