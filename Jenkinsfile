pipeline {
    agent any
    stages {
        stage('build-windows') {
            when {
                not { isUnix }
            }
            steps {
                bat 'echo "building on windows"'
            }
        }
        stage('build-unix') {
            when {
                isUnix
            }
            steps {
                sh 'echo "building on unix"'
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
