#!groovy

import java.text.SimpleDateFormat

node(){
    def dateFormat = new SimpleDateFormat("yyyyMMddHHmm")
    def dockerTag = dateFormat.format(new Date())
    def registry = 'registry.cn-beijing.aliyuncs.com'
    def dockerName='marco_images/image-test'
    def sshIP='8.140.26.173'

    stage('get souce code') {
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

    stage('build and upload Image') {
        withCredentials([usernamePassword(credentialsId: 'jenkins_login_aliyun_docker', usernameVariable: 'username', passwordVariable: 'password')]) {
            try {
                sh 'pwd'
                sh 'ls'
                sh 'cp -r dist ./devops_build'

                sh "docker login -u ${username} -p ${password} ${registry}"
                sh "docker build -t ${registry}/${dockerName}:${dockerTag} ./devops_build"
                sh "docker tag ${registry}/${dockerName}:${dockerTag} ${registry}/${dockerName}:${dockerTag}"
                sh "docker push ${registry}/${dockerName}:${dockerTag}"
                sh "docker rmi ${registry}/${dockerName}:${dockerTag}"
            }
            catch(err) {
                echo "build and upload Image failed"
                throw err
            }

            try {
                def sshServer = getServer(sshIP)
                // 更新或下载镜像
                sshCommand remote: sshServer, command: "docker pull ${registry}/${dockerName}:${dockerTag}"
            }
            catch(err){
                echo "remote & pull image failed"
                throw err
            }
        }
    }
}

def getServer(ip){
    def remote = [:]
    remote.name = "server-${ip}"
    remote.host = ip
    remote.port = 22
    remote.allowAnyHosts = true
    withCredentials([usernamePassword(credentialsId: 'ssh_remote_server', passwordVariable: 'password', usernameVariable: 'userName')]) {
        remote.user = "${userName}"
        remote.password = "${password}"
    }
    return remote
}
