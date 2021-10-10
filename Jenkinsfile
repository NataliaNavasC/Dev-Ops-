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
                sh 'apt-get install python -y'
                sh 'python --version'
            }
        }
    }
}
