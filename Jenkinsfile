#!groovy

node(){
    stage('Get Souce Code'){
        try {
            PrintMessage("get source code", "green")
            checkout scm
        }
        catch(err) {
            PrintMessage("get source code failed", "red")
            throw err
        }
    }

    state('npm install'){
        try{
            PrintMessage("npm 获取依赖","green")
            sh "npm --registry https://registry.npm.taobao.org install"
            }
        catch(err){
                PrintMessage("npm 获取依赖失败","red")
                SendEmail("npm 获取依赖失败")
                throw err
            }
    }

    stage('Build code') {
        try{
                PrintMessage("Dev Test Package","green")
                sh "npm run build"
            }catch(err){
                PrintMessage("Build code失败","red")
                throw err
            }
    }
}

def PrintMessage(value,color){
    colors = [
                    'red'   : "\033[40;31m >>>>>>>>>>>${value}<<<<<<<<<<< \033[0m",
                    'blue'  : "\033[47;34m ${value} \033[0m",
                    'green' : "[1;32m>>>>>>>>>>${value}>>>>>>>>>>[m"
            ]
    ansiColor('xterm') {
        println(colors[color])
    }
}