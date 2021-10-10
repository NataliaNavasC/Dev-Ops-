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
                sh 'apt-get install -y software-properties-common'
                sh 'add-apt-repository ppa:deadsnakes/ppa'
                sh 'apt update'
                sh 'apt install python3.10'
                sh 'python --version'
            }
        }
        stage('deploy') {
            steps {
                sh 'python manage.py makemigrations projects'
                sh 'manage.py migrate projects'
                sh 'manage.py runserver'
            }
        }
    }
}
