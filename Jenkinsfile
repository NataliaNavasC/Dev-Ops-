pipeline {
    agent any
    stages {
        stage('Migration') {
            steps {
                dir('./rp-portfolio') {
                    sh 'python3 manage.py makemigrations projects'
                    sh 'python3 manage.py migrate projects'
                }
            }
        }
        stage('Set up') {
            steps {
                sh 'ls -l'
                sh 'cp -r ./rp-portfolio /deploy'
            }
        }
        stage('Pylint') {
            steps {
                sh 'python3 -m pip install pylint'
                sh 'pylint ./rp-portfolio'
            }
        }
    }
}
