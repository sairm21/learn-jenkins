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

            input {
                message "Should we continue?"
                ok "Yes, we should."
                }
        environment {
                        creds = credentials('Workstation')
                    }
            steps {
                sh 'whoami'
                sh 'printenv'
                echo 'pollSCM testing'
            }
        }

        stage('Example Deploy') {
            when {
                branch 'prod'
            }
            steps {
                echo 'testing when condition'
            }
        }
    }

    post {
            always {
                echo 'post section'
            }
        }
}