pipeline{
    agent any
    stages{
        stage('Clean Workspace'){
            steps{
                cleanWs()
            }
        }
        // stage('dependency check'){
        //     steps{
        //         sh 'wget https://github.com/jeremylong/DependencyCheck/releases/download/v6.3.1/dependency-check-6.3.1-release.zip'
        //         sh 'unzip dependency-check-6.3.1-release.zip'
        //         sh 'ls -al'
        //         echo "================"
        //         dir('dependency-check/bin/'){
        //             sh 'ls -al'
        //             sh 'bash dependency-check.sh --project "test" --format "XML" --scan "../../src/"'
        //         }
        //     }
        // }
        // stage('dependency check publish'){
        //     steps{
        //         dir('dependency-check/bin/'){
        //             sh 'ls -al'
        //             dependencyCheckPublisher pattern: ''
        //         }
        //     }
        // }
        stage('Build'){
            steps{
                sh 'mvn -B -DskipTests clean package'
                
            }
        }
        stage('Dep'){
            steps{
                sh 'echo "java -Dserver.port=8082 -jar target/*.jar" | at now + 1 minutes'
            }
        }    
    }
}