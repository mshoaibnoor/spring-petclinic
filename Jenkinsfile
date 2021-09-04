pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                sh 'mvn -B -DskipTests clean package'
                sh 'java -jar target/*.jar --port=8888'
            }
        }
    }
}