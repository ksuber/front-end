pipeline {
    agent any
    tools {
            nodejs 'nodejs'
        }

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh "npm install"
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh "npm install npm run test"
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                sh "npm install npm run package"
                archiveArtifacts artifacts: '**/distribution/*.zip', fingerprint: true
            }
        }
    }
}