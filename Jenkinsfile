pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Clonar el repositorio
                git 'https://github.com/yesvitale/semana3.git'
            }
        }
        
        stage('Build Docker Image') {
            steps {
                script {
                    //imagen de Docker
                    sh 'docker build -t my-python-app .'
                }
            }
        }
        
        stage('Run Docker Container') {
            steps {
                script {
                    // ejecutar contenedor
                    sh 'docker run -d -p 5000:5000 my-python-app'
                }
            }
        }
    }

    post {
        always {
            echo 'Pipeline finalizado'
        }
        success {
            echo 'Ejecutado con éxito'
        }
        failure {
            echo 'Hay un error.'
        }
    }
}
