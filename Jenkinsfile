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
    
     stage('Deploying') {
         environment {
                ANYPOINT_CREDENTIALS = credentials("deploy-anypoint-user")
                    }
            steps {
                bat "mvn clean package -DskipTests deploy -Dusername=${ANYPOINT_CREDENTIALS_USR} -Dpassword=${ANYPOINT_CREDENTIALS_PSW} -Denvironment=Sandbox -Dmule.version=4.4.0 -Dworkers=1 -Dworker.type=Micro -Dapplication.name=hoopa-udaan-day36-CI-CD -DmuleDeploy -Denv=developer"
            
            }
        }
    }
}
