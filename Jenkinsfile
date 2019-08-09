pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                bat 'copy "%userprofile%\\file.bat" file.bat'
                bat 'echo "copied file bat"'
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
