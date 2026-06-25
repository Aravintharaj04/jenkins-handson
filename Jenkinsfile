@Library('shared-library') _

pipeline {

    agent any

    tools {
        nodejs "Node app"
    }

    stages {

        stage('version increment') {
            steps {
                incrementVersion()
            }
        }

        stage('Run tests') {
            steps {
                runTests()
            }
        }

        stage('Build and Push docker image') {
            steps {
                buildAndPushImage()
            }
        }

        stage('commit version update') {
            steps {
                commitVersionUpdate()
            }
        }
    }
}