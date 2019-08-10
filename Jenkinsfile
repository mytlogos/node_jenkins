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

node {
    stage("build"){
        if (isUnix()){
            sh 'cp ~\\file.bat file.bat'
            sh 'echo "copied file bat on unix"'
        }else{
            bat 'copy "%userprofile%\\file.bat" file.bat'
            bat 'echo "copied file bat on windows"'
        }
    }
    stage("post-build"){
        if (currentBuild.result == null || currentBuild.result == 'SUCCESS'){
            if (isUnix()){
                sh 'echo "post build on unix"'
            }else{
                bat 'copy "%userprofile%\\file.bat" file.bat'
                bat 'echo "copied file bat on windows"'
            }
        }
    }
}
