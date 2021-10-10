pipeline {
    agent any
    stages {
        stage('deploy') {
            steps {
                sh 'ls -l'
                sh 'cp -r ./rp-portfolio /deploy'
                sh 'cd /deploy'
                sh 'ls -l'
            }
        }
    }
}
