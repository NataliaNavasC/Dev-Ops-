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
                sh 'apt update -y'
                sh 'apt install -y software-properties-common'
                sh 'add-apt-repository ppa:deadsnakes/ppa'
                sh 'apt install python3.10'
                sh 'python --version'
            }
        }
    }
}
