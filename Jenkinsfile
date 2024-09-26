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
                sh 'chmod +x os_detector.py'
                sh 'python3.11 os_detector.py'
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
