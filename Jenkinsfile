#!groovy

pipeline {
    agent {
        docker {
            image 'node:10.20.1-alpine3.11' 
            args '-v $HOME/.m2:/root/.m2'
        }

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
                echo "Dev Test Package","green" 
                sh "npm run build"
            }catch(err){
                echo "Build code失败"
                throw err
            }
    }
}
