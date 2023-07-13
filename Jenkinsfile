pipeline {
    agent{
        docker {
            image 'maven:3.9.3-eclipse-temurin-17'
            args '-v ~/.m2:/root/.m2'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh "mvn --version"
                sh "mvn -B -DskipTests clean package"
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}