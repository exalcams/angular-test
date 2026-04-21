pipeline {
    agent any
    tools {
        nodejs 'node' // Name configured in Global Tool Configuration
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/exalcams/angular-test'
            }
        }
        stage('Install Dependencies') {
            steps {
                bat 'npm install' // Use 'sh' on Linux
            }
        }
        stage('Build') {
            steps {
                bat 'npm run build --configuration=production'
            }
        }
        stage('Deploy to IIS') {
            steps {
                // Adjust physical path to your IIS site root
                bat 'xcopy /s /y "dist\\angular-test\\*" "C:\\inetpub\\wwwroot\\angular-test"'
            }
        }
    }
}
