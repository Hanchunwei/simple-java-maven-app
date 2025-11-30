pipeline {
    agent any

    tools {
        maven 'Maven 3.9.11'   // ← 替换为你的实际 Name！
    }

    stages {
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
      stage('Docker Build') {
                 steps {
//                      sh 'docker build -t myapp:${BUILD_NUMBER} .'
                        sh '/usr/bin/docker build -t myapp:${BUILD_NUMBER} .'
            }
        }
    }
}