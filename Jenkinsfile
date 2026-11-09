pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
                bat 'git status'
            }
        }
        stage('Build') {
            steps {
                bat 'echo Build en cours...'
                bat 'dir'
            }
        }
        stage('Test') {
            steps {
                bat 'if not exist index.html exit 1'
                bat 'if not exist style.css exit 1'
                bat 'findstr "Bienvenue" index.html'
                bat 'echo Test OK'
            }
        }
        stage('Delivery') {
            steps {
                archiveArtifacts artifacts: '**/*.html, **/*.css'
            }
        }
        stage('Post Actions') {
            steps {
                echo 'Pipeline termine avec succes !'
            }
        }
    }
}