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
                sh 'apt-get -y upgrade'
                sh 'apt-get update'
                sh 'apt-get install python3 -y'
            }
        }
        stage('deploy') {
            steps {
                sh 'python3 manage.py makemigrations projects'
                sh 'python3 manage.py migrate projects'
                sh 'python3 manage.py runserver'
            }
        }
    }
}
