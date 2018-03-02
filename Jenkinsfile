#!groovy

pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                sh '''#!/bin/bash -l
                yarn && yarn test
                '''
            }
        }
        stage('Build') {
            steps {
                sh '''#!/bin/bash -l
                yarn build
                '''
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
