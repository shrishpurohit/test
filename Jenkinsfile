pipeline {
    agent any
    environment
    {
        simplename = 'withscript'
    }
    stages {
        stage('checkout') {
            steps {
                checkout scm
            }
        }
        stage('build') {
            steps {
                sh 'docker build -t ${env.simplename} .'
            }
        }
        stage('run') {
            steps {
                sh 'docker run ${env.simplename}' 
            }
        }
    }
}
