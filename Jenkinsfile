pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git branch : 'main',url : 'https://github.com/PrekshaPS04/jd7.git'
            }
        }
        stage('Install') {
            steps {
                bat 'npm install'
            }
        }
        stage('Run App') {
            steps {
                bat 'node app.js'
            }
        }
        stage('test') {
            steps {
                bat 'node test.js'
            }
        }
        stage('Build iamge') {
            steps {
                bat 'docker build -t home7 .'
            }
        }
        stage('Run Container') {
            steps {
                bat 'docker run -d -p 3000:3000 --name home7container home7'
            }
        }
    }
}