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

    stage('npm run build'){
        try{
            docker.image('node:12-alpine').inside {
                sh 'node --version'
                sh 'npm --version'
                sh "npm install -g cnpm --registry=https://registry.npm.taobao.org"
                sh 'cnpm install'
                sh 'cnpm run build'
            }
            }
        catch(err){
                echo "npm run build failed"
                throw err
            }
    }
}
