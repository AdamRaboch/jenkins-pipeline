pipeline {
    agent any
    stages {
        stage('Get code from GitHub') {
            steps {
                git 'https://github.com/AdamRaboch/time-date'
            }
        }
        stage('Run') {
            steps {
                sh 'python3 time.py'
            }
        }
    }
}
