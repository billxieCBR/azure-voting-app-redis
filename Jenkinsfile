pipeline {
    agent any

    stages {
        stage('verify Branch') {
            steps {
                echo "$GIT_BRANCH"
            }
        }
    stage('Dock Build') {
            steps {
                sh(script: 'docker images -a')
                sh(script: """
                cd azure-vote
                docker images -a
                dock build -t jenkins-pipeline .
                docker images -a
                cd ..
                """)
            }
        }





    }
}
