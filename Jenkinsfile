pipeline {
    agent any
    stages {
        stage('set up') {
            steps {
                sh 'ls -l'
                sh 'cp ./rp-portfolio /deploy'
                sh 'cd /deploy'
                sh 'ls -l'
            }
        }
        stage('python config') {
            steps {
                sh 'apt-get install python3.10'
                sh 'python --version'
            }
        }
    }
}
