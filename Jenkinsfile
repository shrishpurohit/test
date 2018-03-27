pipeline {
    agent any
    environment
    {
        SIMPLENAME = 'withscript'
    }
    stages {
        stage('checkout') {
            steps {
                checkout scm
            }
        }
        stage('build') {
            steps {
                sh 'docker build -t ${env.SIMPLENAME} .'
            }
        }
        stage('run') {
            steps {
                sh 'docker run ${env.SIMPLENAME}' 
            }
        }
    }
}
