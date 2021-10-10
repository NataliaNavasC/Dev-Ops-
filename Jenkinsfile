pipeline {
    agent any
    stages {
        stage('set up') {
            steps {
                sh 'ls -l'
                sh 'cp -i ./rp-portfolio /deploy'
            }
        }
        stage('python config') {
            steps {
                sh 'apt-get install python3 -y'
                sh 'python --version'
            }
        }
        stage('deploy') {
            steps {
                sh 'ls -l'
                sh 'cd ./rp-portfolio'
                sh 'ls -l'
                sh 'cd ./rp-portfolio'
                sh 'ls -l'
                sh 'python manage.py makemigrations projects'
                sh 'manage.py migrate projects'
                sh 'manage.py runserver'
            }
        }
    }
}
