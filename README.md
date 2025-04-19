*Created a GitHub repository named ABC-1611
*Cloned the repository locally using:
git clone https://github.com/maheshgowdan-hub/ABC-1611.git
*Created a Maven web application using the archetype-webapp template:
mvn archetype:generate -DgroupId=com.example -DartifactId=my-webapp -DarchetypeArtifactId=maven-archetype-webapp -DarchetypeVersion=1.4 -DinteractiveMode=false
*Created a Jenkins pipeline (http://20.42.19.182:8080/)
-Build the project: sh 'mvn clean install'
-push and deploy to tomcat: 
