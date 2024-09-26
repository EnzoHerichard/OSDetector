pipeline {
    agent any

    stages {
        stage('Get the Code !') {
            steps {
                git branch: 'main', url: 'https://github.com/EnzoHerichard/OSDetector.git'
            }
        }

        stage('Setting permissions and running the script') {
            steps {
                sh 'chmod +x OSDetector.py'
                sh 'python3 OSDetector.py'
            }
        }
    }

    post {
        success {
            echo 'It worked, you Geniuuuus !'
        }
        failure {
            echo 'Ohh god, we are in troubles'
        }
    }
}
