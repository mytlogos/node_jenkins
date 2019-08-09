pipeline {
    agent any
    stages {
        stage('build-windows') {
            when {
                not {
                    expression {
                        isUnix
                    }
                }
            }
            steps {
                bat 'echo "building on windows"'
            }
        }
        stage('build-unix') {
            when {
                expression {
                    isUnix
                }
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
