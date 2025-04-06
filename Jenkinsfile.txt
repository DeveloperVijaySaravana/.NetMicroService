pipeline {
    agent any
    stages {
        stage('Checkout Code') {
            steps {
                checkout scm
            }
        }
        stage('Build Project') {
            steps {
                dir('UserService/UserService') { 
                    sh 'dotnet build 1_API.csproj'
                }
            }
        }
    }
}