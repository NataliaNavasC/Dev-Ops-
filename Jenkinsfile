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
                sh 'ls -l'
                sh 'cd ./rp-portfolio'
                sh 'ls -l'
                sh 'cd ./rp-portfolio'
                sh 'ls -l'
                sh 'cd ./rp-portfolio'
                sh 'ls -l'
                sh 'python ./rp-portfolio/manage.py makemigrations projects'
                sh './rp-portfolio/manage.pymanage.py migrate projects'
                sh './rp-portfolio/manage.pymanage.py runserver'
            }
        }
    }
}
