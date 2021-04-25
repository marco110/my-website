#!groovy

node(){
    stage('Get Souce Code'){
        try {
            echo "get source code"
            checkout scm
        }
        catch(err) {
            echo "get source code failed"
            throw err
        }
    }

    stage('npm install'){
        try{
            echo "npm 获取依赖"
            sh "npm --registry https://registry.npm.taobao.org install"
            }
        catch(err){
                echo "npm 获取依赖失败"
                throw err
            }
    }

    stage('Build code') {
        try{
                echo "Build code"
                sh "npm run build"
            }catch(err){
                echo "Build code失败"
                throw err
            }
    }
}
