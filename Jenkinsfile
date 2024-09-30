pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Clonar el repositorio
                git 'https://github.com/yesvitale/semana3.git' // Cambia esta URL
            }
        }
        
        stage('Build Docker Image') {
            steps {
                script {
                    // Construir la imagen de Docker
                    sh 'docker build -t my-python-app .'
                }
            }
        }
        
        stage('Run Docker Container') {
            steps {
                script {
                    // Ejecutar el contenedor
                    sh 'docker run -d -p 5000:5000 my-python-app'
                }
            }
        }
    }

    post {
        always {
            echo 'Pipeline completado.'
        }
        success {
            echo '¡Pipeline ejecutado con éxito!'
        }
        failure {
            echo 'Hubo un error en el pipeline.'
        }
    }
}
