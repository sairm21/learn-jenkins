pipeline {
    agent { node { label 'Workstation' } }

    environment {
            CC = 'clang'
        }

    options {
        ansiColor('xterm')
    }

/*
    parameters {
            string(name: 'app_name', defaultValue: 'roboshop', description: 'enter application name')
            }
 */

    triggers { pollSCM('H/2 * * * *') }

    stages {
        stage('stage-1') {
        environment {
                        creds = credentials('Workstation')
                    }
            steps {
                sh 'whoami'
                sh 'printenv'
                echo 'pollSCM testing'
            }
        }
    }

    post {
            always {
                echo 'post section'
            }
        }
}