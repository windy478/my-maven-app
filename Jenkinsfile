pipeline {
    agent any
    tools {
        maven 'Maven 3.8.6'
        jdk 'JDK11'
    }
    stages {
        stage('Checkout Git') {
            steps {
                echo 'Checking out code from GitHub...'
            }
        }
        stage('Build & Test') {
            steps {
                // Chạy lệnh test của Maven
                sh 'mvn clean test'
            }
        }
    }
    post {
        always {
            // Thu thập kết quả JUnit test để hiển thị lên Jenkins
            junit '**/target/surefire-reports/*.xml'
        }
    }
}
