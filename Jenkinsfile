node {
    stage("build"){
        if (isUnix()){
            sh 'echo "copied file bat on unix"'
            sh '$PATH'
            sh 'npm -v'
        }else{
            bat 'copy "%userprofile%\\file.bat" file.bat'
            bat 'echo "copied file bat on windows"'
            bat 'npm -v'
        }
    }
    stage("post-build"){
        if (currentBuild.result == null || currentBuild.result == 'SUCCESS'){
            if (isUnix()){
                sh 'echo "post build on unix"'
            }else{
                bat 'echo "post build on windows"'
            }
        }
    }
}
