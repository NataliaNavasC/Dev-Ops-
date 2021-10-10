pipeline {
    agent any
    stages {
        stage('Set up') {
            steps {
                sh 'cp -r ./rp-portfolio /deploy'
            }
        }
        stage('Python config') {
            steps {
                sh 'apt-get -y upgrade'
                sh 'apt-get update'
                sh 'apt-get install python3 -y'
            }
        }
        stage('Django config') {
            steps {
                sh 'apt-get install python3-pip -y'
                sh 'python3 -m pip install Django'
            }
        }
        stage('Migration') {
            steps {
                dir('./rp-portfolio') {
                    sh 'python3 manage.py makemigrations projects'
                    sh 'python3 manage.py migrate projects'
                }
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
