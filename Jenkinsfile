/*
pipeline {
    agent { node { label 'Workstation' } }

    environment {
            CC = 'clang'
        }

    options {
        ansiColor('xterm')
    }

 */
/*
    parameters {
            string(name: 'app_name', defaultValue: 'roboshop', description: 'enter application name')
            }
 *//*


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
                branch 'main'
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
} */

pipeline {
    agent any
    stages {
        stage('Non-Parallel Stage') {
            steps {
                echo 'This stage will be executed first.'
            }
        }
        stage('Parallel Stage') {
            failFast true
            parallel {
                stage('Branch A') {
                    agent { node { label 'Workstation' } }
                    steps {
                        echo "On Branch A"
                    }
                }
                stage('Branch B') {
                    agent { node { label 'Workstation' } }
                    steps {
                        echo "On Branch B"
                    }
                }
                stage('Branch C') {
                    agent { node { label 'Workstation' } }
                    stages {
                        stage('Nested 1') {
                            steps {
                                echo "In stage Nested 1 within Branch C"
                            }
                        }
                        stage('Nested 2') {
                            steps {
                                echo "In stage Nested 2 within Branch C"
                            }
                        }
                    }
                }
            }
        }
    }
}