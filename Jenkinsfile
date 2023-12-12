pipeline {
    agent { node { label 'Workstation' } }
    environment {
            CC = 'clang'
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