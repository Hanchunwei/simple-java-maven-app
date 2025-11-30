pipeline {
    agent any
    environment {
        // 强制指定 known_hosts 路径
        GIT_SSH_COMMAND = 'ssh -o UserKnownHostsFile=/var/jenkins_home/.ssh/known_hosts -o IdentitiesOnly=yes'
    }
    stages {
        stage('Checkout') {
            steps {
                checkout([
                    $class: 'GitSCM',
                    branches: [[name: '*/main']],
                    doGenerateSubmoduleConfigurations: false,
                    userRemoteConfigs: [[
                        url: 'git@github.com:Hanchunwei/simple-java-maven-app.git',
                        credentialsId: '6d4c042d-e973-41d3-abae-e17f63392825' // 替换为你的凭据 ID
                    ]]
                ])
            }
        }
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
    }
}