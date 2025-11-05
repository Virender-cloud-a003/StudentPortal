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
                bat '"C:\\Users\\thaku\\AppData\\Local\\Programs\\Python\\Python314\\python.exe" -m pip install --upgrade pip'
                bat '"C:\\Users\\thaku\\AppData\\Local\\Programs\\Python\\Python314\\python.exe" -m pip install -r requirements.txt'
            }
        }

        stage('Run Flask App') {
            steps {
                bat '"C:\\Users\\thaku\\AppData\\Local\\Programs\\Python\\Python314\\python.exe" app.py'
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
