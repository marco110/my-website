#!groovy

node(){
    stage('Get Souce Code') {
        try {
            echo "get source code"
            checkout scm
        }
        catch(err) {
            echo "get source code failed"
            throw err
        }
    }

    stage('npm run build') {
        try{
            docker.image('node:12-alpine').inside {
                sh 'node --version'
                sh 'npm --version'
                sh "npm --registry https://registry.npm.taobao.org install"
                sh 'npm install'
                sh 'npm run build'
            }
            }
        catch(err){
                echo "npm run build failed"
                throw err
            }
    }

    stage('deploy with Nginx') {
        try {
            sh 'cp -r "dist" "./devops_build/dist"'
            sh "docker build -t docker-test-new:v1 ./devops_build"
            sh "docker run -u root --name docker-test-new-v1 -p 8000:8000 -it -d nginx:1.17.3-alpine"
        }
        catch(err){
                echo "deploy with Nginx failed"
                throw err
            }
    }
}
