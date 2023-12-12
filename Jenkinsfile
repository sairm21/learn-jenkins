pipeline {
    agent { node { label 'Workstation' } }

    stages {
        stage('stage-1') {
            steps {
                sh 'whoami'
            }
        }
    }
    post {
            always {
                echo 'post section'
            }
        }
}