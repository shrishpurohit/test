pipeline {
    agent any
    enviornment {
        name = 'withscript'
    }
    stages {
        stage('checkout') {
            steps {
                checkout scm
            }
        }
        stage('build') {
            steps {
                sh 'docker build -t ${env.name} .'
            }
        }
        stage('run') {
            steps {
                sh 'docker run ${env.name}' >> results.txt
            }
        }
        stage('check post') {
            steps {
                def output=readFile('result').trim()
                echo "output=$output";

            }
        }
    }
}
