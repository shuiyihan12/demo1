pipeline {
    agent{
        docker.image('maven:3.9.3-eclipse-temurin-8').inside {
          git 'https://github.com/shuiyihan12/demo1.git'
          writeFile file: 'settings.xml', text: "<settings><localRepository>${pwd()}/.m2repo</localRepository></settings>"
          sh 'mvn -B -s settings.xml clean install'
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