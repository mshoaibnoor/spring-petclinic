pipeline{
    agent any
    stages{
        stage('Clean Workspace'){
            steps{
                cleanws()
            }
        }
        stage('Build'){
            steps{
                sh 'mvn -B -DskipTests clean package'
                
            }
        }
        stage('Deploy'){
            Steps{
                sh 'echo "java -Dserver.port=8082 -jar target/*.jar" | at now + 1 minutes'
            }
        }    
    }
}