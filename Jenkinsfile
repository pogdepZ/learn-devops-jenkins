pipeline {
    agent any

     tools {
        nodejs 'node18'
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out source code...'
                // Trong thực tế, Jenkins sẽ tự động clone code từ Git về workspace của build job
            }
        }

        stage('Install') {
            steps {
                echo 'Installing dependencies...'
                // Lệnh npm install cài đặt các thư viện trong package.json nếu có
                // Dùng lệnh 'npm install' hoặc 'npm ci'
                sh 'npm install'
            }
        }

        stage('Test') {
            steps {
                echo 'Running test phase...'
                // Lệnh chạy kiểm thử NodeJS thực tế theo yêu cầu
                sh 'node app.js'
            }
        }

        stage('Build') {
            steps {
                echo 'Building application...'
                // NodeJS không cần compile, stage này chủ yếu mô phỏng đóng gói hoặc tối ưu hóa
                echo 'Build process completed!'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application to environment...'
                // Yêu cầu in ra dòng chữ "Deploy successful"
                echo 'Deploy successful'
            }
        }
    }

    post {
        always {
            echo 'CI/CD Pipeline has finished execution.'
        }
        success {
            echo 'Pipeline status: SUCCESS!'
        }
        failure {
            echo 'Pipeline status: FAILED! Please check logs.'
        }
    }
}
