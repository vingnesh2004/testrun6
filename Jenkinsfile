pipeline {  
    agent any 
    stages { 
        stage('Build Application') { 
            steps { 
                bat 'mvn clean install' 
            } 
        } 
        stage('Deploy to CloudHub') { 
            environment { 
                ANYPOINT_CREDENTIALS = credentials('anypointplatformcredentials') 
            } 
            steps { 
                echo 'Deploying Mule project due to the latest code commit…' 
                echo 'Deploying to the configured environment…' 
                bat 'mvn clean deploy -DmuleDeploy'
            }  
        } 
    } 
}
