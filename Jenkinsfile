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
        when {
             expression {
                 currentBuild.result == null || currentBuild.result == 'SUCCESS'
             }
        }
        if (isUnix()){
            sh 'echo "post build on unix"'
        }else{
            bat 'copy "%userprofile%\\file.bat" file.bat'
            bat 'echo "copied file bat on windows"'
        }
    }
}
