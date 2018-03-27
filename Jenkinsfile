pipeline {
    agent any
    environment
    {
        SIMPLENAME = 'withscript'
    }
    stages {
        stage('checkout') {
            steps {
                //checkout scm
                git url: 'git@github.com:shrishpurohit/test.git',
                    branch: 'master',
                    credentialsId: 'gh-d--dbase'
                sh "pwd"
                sh "ls"
            }
        }
        stage('build') {
            steps {
                sh "docker build -t ${env.SIMPLENAME} ."
            }
        }
        stage('run') {
            steps {
                sh "docker run ${env.SIMPLENAME}" 
            }
        }
    }
}
