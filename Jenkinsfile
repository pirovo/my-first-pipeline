pipeline {
agent any
stages {
stage('Build') {
steps {
sh 'npm install --unsafe-perm'
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
