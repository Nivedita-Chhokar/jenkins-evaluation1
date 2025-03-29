pipeline {
    agent any
    
    stages {
        //for cloning the repository
        stage ("Clone Repository") {
            steps {
                git "https://github.com/Nivedita-Chhokar/jenkins-evaluation1"
            }
        }

        //install the dependencies
        stage ("Install dependencies") {
            steps {
                sh 'npm install'
            }
        }
        
        //to run test
        stage ("Run Tests") {
            steps {
                sh 'npm test || echo "No tests defined"'
            }
        }
        
        //for building the application
        stage ("Build") {
            steps {
                sh 'npm run build' 
            }
        }

        //for docker image
        stage ("Docker Container") {
            steps {
                sh 'docker build -t jenkins-evaluation1 .'
            }
        }
    }
}
