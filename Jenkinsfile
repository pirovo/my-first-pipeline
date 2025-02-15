pipeline {
agent any
stages {
stage('Build') {
steps {
sh 'node -v'
sh 'npm -v'
sh 'npm cache clean --force'
sh 'npm install -g npm@8'

//sh 'npm install'
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
