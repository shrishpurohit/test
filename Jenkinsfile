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
                    credentialsId: '34649ee9-1c8d-483c-b304-45220fe49a6b'
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
            agent {
                docker {
                    image 'withscript'
                }
            }
            steps {
                script {
                    sh "echo 'in IMAGE'"
                    sh "python echo.py"
                }
            }
        }
    }
}
