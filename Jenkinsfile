pipeline {
    agent any

    stages {
        stage('Clonar Repositorio') {
            steps {
                git 'https://github.com/TU_USUARIO/jenkins-test-app.git'
            }
        }

        stage('Instalar Dependencias') {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Ejecutar Pruebas') {
            steps {
                sh 'pytest --maxfail=1 --disable-warnings'
            }
        }

        stage('Desplegar') {
            steps {
                sh 'nohup python app.py &'
            }
        }
    }
}
