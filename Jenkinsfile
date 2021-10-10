pipeline {
    agent any
    stages {
        stage('set up') {
            steps {
                sh 'ls -l'
                sh 'cp -r ./rp-portfolio /deploy'
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
                sh 'cd rp-portfolio'
                sh 'python manage.py makemigrations projects'
                sh 'manage.py migrate projects'
                sh 'manage.py runserver'
            }
        }
    }
}
