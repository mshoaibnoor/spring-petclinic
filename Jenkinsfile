pipeline{
    agent any
    stages{
        stage('Clean Workspace'){
            steps{
                cleanWs()
            }
        }
        stage('Build'){
            steps{
                sh 'mvn -B -DskipTests clean package'
                sh 'echo "java -Dserver.port=8082 -jar target/*.jar" | at now + 1 minutes'
            }
        }
            
    }
}