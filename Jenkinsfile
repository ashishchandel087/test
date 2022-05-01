pipeline {
    agent any

    tools {
        maven "Maven"
        jdk "Java"
    }

    stages {
        
        stage('Building') {
            steps {
                bat "mvn clean install"
            
            }
        }
    }
}
