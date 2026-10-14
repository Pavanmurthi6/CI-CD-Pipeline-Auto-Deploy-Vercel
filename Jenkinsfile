pipeline {
    agent any

    environment {
        VERCEL_TOKEN = credentials('vercel_token')
    }

    stages {
        stage('Install') {
            steps {
                bat 'npm installs'
            }
        }
        stage('Test') {
            steps {
                echo 'Skipping tests - no test script found'
            }
        }
        stage('Build') {
            steps {
                bat 'npm run build'
            }
        }
        stage('Deploy') {
            steps {
                bat 'npx vercel --prod --yes --token=%VERCEL_TOKEN%'
            }
        }
    }
}