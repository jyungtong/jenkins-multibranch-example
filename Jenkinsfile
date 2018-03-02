#!groovy

pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                sh 'yarn && yarn test'
            }
        }
        stage('Build') {
            steps {
                sh 'yarn build'
            }
        }
        stage('Deploy Development') {
            when {
                branch 'master'
            }
            steps {
                echo 'deploy to development env...'
            }
        }
        stage('Deploy Production') {
            when {
                branch 'production'
            }
            steps {
                echo 'deploy to production env...'
            }
        }
    }
}
