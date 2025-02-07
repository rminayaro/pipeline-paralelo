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
                sh 'echo "Compilando código..."'
                sh 'echo "Ejecutando pruebas..."'
            }
        }

        stage('Subir a Nexus') {
            steps {
                sh 'echo "Subiendo imagen a Nexus..."'
            }
        }

        stage('Desplegar en Servidor') {
            when {
                branch 'main'
            }
            steps {
                sh 'echo "Desplegando en el servidor..."'
            }
        }
    }
}
