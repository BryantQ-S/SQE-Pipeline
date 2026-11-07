pipeline {
    agent any
    triggers { pollSCM('H/2 * * * *') }
    tools { nodejs 'NodeJS-20' }
    environment {
        STUDENT_NAME = 'Bryant Sy'
    }
    stages {
        stage('Checkout') {
            steps { checkout scm }
        }
        stage('Install Dependencies') {
            steps { sh 'npm install' }
        }
        stage('Run Tests') {
            steps { sh 'npm test' }
        }
        stage('Report') {
            steps { echo "Pipeline run by ${env.BRYANT_SY}" }
        stage('Show Versions') {
            steps {
                sh 'node -v && npm -v'
                echo "Build finished for ${env.BRYANT_SY}"
                }
            }
        }
    }
    post {
        success { echo 'Build succeeded: all tests passed.' }
        failure { echo 'Build failed: check the failed stage in Console Output.' }
    }
}
