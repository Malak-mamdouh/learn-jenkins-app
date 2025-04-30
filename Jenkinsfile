pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                bat 'docker pull node:18-alpine'
                reuseNode true // to share the same workspace between stages because by default docker does not share workspace 
                bat '''
                    dir
                    node --version
                    npm ci
                    npm run build
                '''
            }
        }
    }
}
