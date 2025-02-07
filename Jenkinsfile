pipeline {
    agent any

    stages {
        stage('Descargar Código') {
            steps {
                git branch: 'main', url: 'https://github.com/rminayaro/pipeline-paralelo.git'
            }
        }

        stage('Construir y Probar') {
            steps {
                bat 'echo "Compilando código..."'
                bat 'echo "Ejecutando pruebas..."'
            }
        }

        stage('Subir a Nexus') {
            steps {
                bat 'echo "Subiendo imagen a Nexus..."'
            }
        }

        stage('Desplegar en Servidor') {
            when {
                branch 'main'
            }
            steps {
                bat 'echo "Desplegando en el servidor..."'
            }
        }
    }
}
