pipeline {
    agent any

    parameters {
        booleanParam(name: 'DRY_RUN', defaultValue: false, description: 'Set to true to skip running time.py')
    }

    stages {
        stage('Get code from GitHub') {
            steps {
                git branch: 'main', url: 'https://github.com/AdamRaboch/time-date'
            }
        }
        stage('Run') {
            when {
                expression { return !params.DRY_RUN }
            }
            steps {
                sh 'python3 time.py > output.txt'
            }
        }
        stage('Archive Output') {
            steps {
                archiveArtifacts artifacts: 'output.txt', allowEmptyArchive: true
            }
        }
        stage('Print Output') {
            steps {
                script {
                    def output = readFile('output.txt')
                    echo output
                }
            }
        }
    }
}
