pipeline
{
  agent any
  environment{
    PATH ="/opt/apache-maven-3.6.3/bin:$PATH"
  }
  stages{
    stage('clone')
    {
      steps{
      git branch: 'development', url: 'https://github.com/Rupali1520/jenkinsassignmentrepo.git'
      }}
    stage ('Build') {
      steps {
        sh 'mvn clean install'
      }
    }
     stage('Deploy') {
            environment {
               TOMCAT_HOME = '/opt/tomcat'
            }
            steps {
                sh 'sudo cp /var/lib/jenkins/workspace/try_development/target/java-hello-world.war /opt/tomcat/webapps/'
                sh 'sudo /opt/tomcat/bin/shutdown.sh'
                sh 'sudo /opt/tomcat/bin/startup.sh'
            }
        }
   
    stage('Deploy2') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'tomcat-credentials-id', usernameVariable: 'admin', passwordVariable: 'password')]) {
                    sh "curl -u ${TOMCAT_USER}:${TOMCAT_PASSWORD} --upload-file target/yourproject.war http://localhost:8080/manager/text/deploy?path=/yourproject&update=true"
                }
            }
  }
    
  
}
