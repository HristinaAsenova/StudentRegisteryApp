pipeline{
    agent any

    stages{
        stage('Checkout'){
            steps{
                git branch: 'main', url: 'https://github.com/HristinaAsenova/StudentRegisteryApp'
            }
        }

        stage('Install dependencies'){
            steps{
                script{
                    bat 'npm install'
                }
            }
        }

        stage('Start application and Run tests'){
           steps{
            script{
                bat 'npm start &'
                bat 'wait-on http://localhost:8080'
                bat 'npm test'
            }
           }
        }
    }

    post{
        always{
            echo "CI pepiline completed"
        }
    }
}
