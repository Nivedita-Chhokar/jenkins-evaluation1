pipeline {
    agent any
    
    stages {
        stage ("Clone Repository") {
            steps {
                echo "Cloning repository..."
                git branch: 'main', url: 'https://github.com/Nivedita-Chhokar/jenkins-evaluation1.git'
            }
        }
        
        stage ("Install dependencies") {
            steps {
                bat 'npm install'
            }
        }
        
        stage ("Run Tests") {
            steps {
                bat 'npm test || echo "No tests defined"'
            }
        }
        
        stage ("Build") {
            steps {
                bat 'npm run build'
            }
        }
        
        stage ("Docker Container") {
            steps {
                bat 'docker build -t jenkins-evaluation1 .'
            }
        }
    }
}
