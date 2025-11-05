pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/Virender-cloud-a003/StudentPortal.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                bat 'pip install -r requirements.txt'
            }
        }

        stage('Run Flask App') {
            steps {
                bat 'python app.py'
            }
        }
    }

    post {
        success {
            echo '✅ Build Successful — Flask Student Portal is running!'
        }
        failure {
            echo '❌ Build Failed — Please check the logs.'
        }
    }
}
