pipeline {
    agent any
    tools {
        maven 'Maven 3.9.10'
        jdk 'JDK17'
    }
    stages {
        stage('Clonar') {
            steps {
                checkout scm
           }
       }
       stage('Compilar') {
           steps {
               sh 'mvn clean install'
           }
       }
       stage('Pruebas') {
           steps {
               sh 'mvn test'
           }
        }
 stage('Desplegar') {
    steps {
        sh 'mvn deploy'
    }
}
}
post {
    success {
        echo " El build fue exitoso"
    }
    failure {
        echo " El build falló"
    }
}