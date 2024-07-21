pipeline {
    agent any
    stages {
        stage('Get code from GitHub') {
            steps {
                git branch: 'main', url: 'https://github.com/AdamRaboch/time-date'
            }
        }
        stage('Run') {
            steps {
                sh 'python3 time.py > output.txt'
            }
        }
    }
}
