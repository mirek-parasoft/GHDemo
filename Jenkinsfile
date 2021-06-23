pipeline {
    agent any 
    stages {
        stage('Build') {
            steps {
                echo 'Building stage' 
                sh 'mkdir build && cd build'
                sh 'cmake -DCMAKE_EXPORT_COMPILE_COMMANDS=ON ..'
                sh 'make'
            }
        }
    }
    stages {
        stage('Test') {
            steps {
                echo 'Testing stage' 
            }
        }
    }
    stages {
        stage('Archive stage') {
            steps {
                echo 'Hello world!' 
            }
        }
    }
}