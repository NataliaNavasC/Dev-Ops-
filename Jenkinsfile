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
                sh 'apt install -y build-essential zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev libssl-dev libreadline-dev libffi-dev wget'
                dir('tmp') {
                    sh 'wget https://www.python.org/ftp/python/3.7.5/Python-3.7.5.tgz'
                    sh 'tar -xf Python-3.8.3.tgz'
                    dir('python-3.8.3') {
                        sh './configure --enable-optimizations'
                        sh 'make altinstall'
                        sh 'make install'
                        sh 'python --version'
                    }
                }    
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
