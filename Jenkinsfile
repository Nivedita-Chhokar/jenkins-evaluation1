pipeline {
    agent any

    tools {
        nodejs 'Node 22'
    }
    
    stages {
        //for cloning the repository
        stage ("Clone Repository") {
            steps {
                git "https://github.com/Nivedita-Chhokar/jenkins-evaluation1.git"
            }
        }

        //install the dependencies
        stage ("Install dependencies") {
            steps {
                bat 'npm install'
            }
        }
        
        //to run test
        stage ("Run Tests") {
            steps {
                bat 'npm test || echo "No tests defined"'
            }
        }
        
        //for building the application
        stage ("Build") {
            steps {
                bat 'npm run build' 
            }
        }

        //for docker image
        stage ("Docker Container") {
            steps {
                bat 'docker build -t jenkins-evaluation1 .'
            }
        }
    }
}
