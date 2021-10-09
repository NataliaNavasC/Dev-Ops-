pipeline {
    agent any
    stages {
        stage('deploy') {
            agent {
                docker {
                    image 'python:3-alpine'
                }
            }
            steps {
                sh 'cd rp-portfolio'
                sh 'python -m pip install Django'
                sh 'python manage.py makemigrations projects'
                sh 'python manage.py migrate projects'
                sh 'python manage.py runserver'
            }
        }
    }
}