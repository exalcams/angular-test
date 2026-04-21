pipeline {
    agent any
    tools {
        nodejs 'node' // Name must match the one in Global Tool Configuration
    }
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/exalcams/angular-test'
            }
        }
        stage('Install Dependencies') {
            steps {
                bat 'npm install' // 'bat' is used for Windows command prompt
            }
        }
        stage('Build Angular App') {
            steps {
                bat 'npm run build --prod'
            }
        }
        stage('Deploy') {
            steps {
                // Example: Deploy to local IIS directory
                bat 'xcopy /s /y "dist\\angular-test\\*" "C:\\inetpub\\wwwroot\\angular-test"'
            }
        }
    }
}
