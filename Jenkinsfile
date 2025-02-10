pipeline {
    agent any
    environment {
        VERCEL_TOKEN = credentials('vercel-token')
    }
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/TU_USUARIO/TU_REPO.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }
        stage('Deploy to Vercel') {
            steps {
                sh 'vercel --token $VERCEL_TOKEN --prod'
            }
        }
    }
    post {
        success {
            echo '🚀 Despliegue exitoso en Vercel'
        }
        failure {
            echo '❌ Error en el pipeline, revisa los logs'
        }
    }
}
