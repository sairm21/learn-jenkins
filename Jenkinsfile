pipeline {
    agent { node { label 'Workstation' } }

    environment {
            CC = 'clang'
        }

    options {
        ansiColor('xterm')
    }

    parameters {
            string(app_name: 'name', defaultValue: 'roboshop', description: 'enter application name')
            }


    stages {
        stage('stage-1') {
        environment {
                        creds = credentials('Workstation')
                    }
            steps {
                sh 'whoami'
                sh 'printenv'
            }
        }
    }

    post {
            always {
                echo 'post section'
            }
        }
}