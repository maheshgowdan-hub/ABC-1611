pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        
        stage('Push Artifact') {
            steps {
                sh '''
                mvn deploy:deploy-file \
                  -DgroupId=com.example \
                  -DartifactId=my-webapp \
                  -Dversion=1.0-SNAPSHOT \
                  -Dpackaging=war \
                  -Dfile=target/my-webapp.war \
                  -DrepositoryId=adikarthikgupta \
                  -Durl=https://pkgs.dev.azure.com/adikarthikgupta/_packaging/adikarthikgupta/maven/v1
                '''
            }
        }
        
        stage('Deploy to Tomcat') {
            steps {
                sh 'cp target/my-webapp.war /path/to/tomcat/webapps/'
                // Or use a deploy plugin/script appropriate for your environment
            }
        }
    }
}
