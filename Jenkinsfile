pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                dir('my-webapp') {
                    sh 'mvn clean install'
                }
            }
        }

      /*  stage('Push Artifact') {
            steps {
                dir('my-webapp') {
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
        } */

        stage('Deploy to Tomcat') {
            steps {
                dir('my-webapp') {
                    sh 'cp target/my-webapp.war /home/luffy/apache-tomcat-9.0.104/webapps'
                }
            }
        }
    }
}
