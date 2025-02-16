pipeline {
agent any
stages {
stage('Build') {
steps {
sh 'npm cache clean --force'
sh 'npm install --legacy-peer-deps'
sh 'npm run build'
}
}
stage('Deploy') {
steps {
withCredentials([string(credentialsId: 'vercel-token', variable: 'VERCEL_TOKEN')]) {
sh 'vercel --token $VERCEL_TOKEN --prod'
}
}
}
}
}
