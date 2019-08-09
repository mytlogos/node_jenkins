pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                bat 'echo "building"'
            }
        }
        stage('post-build'){
            when {
                 expression {
                     currentBuild.result == null || currentBuild.result == 'SUCCESS'
                 }
            }
            steps {
                 bat 'echo "post build"'
            }

        }
    }
}
