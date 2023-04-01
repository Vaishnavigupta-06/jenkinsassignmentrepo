pipeline
{
  agent any
  environment{
    PATH ="/opt/apache-maven-3.6.3/bin:$PATH"
    TOMCAT_URL = 'localhost:8080'
    CONTEXT_PATH = '/'
    CREDENTIALS_ID = 'admin'
    WAR_PATTERN = '**/*.war'
  }
  stages{
    stage('clone')
    {
      steps{
      git branch: 'development', url: 'https://github.com/Rupali1520/jenkinsassignmentrepo.git'
      }}
    stage ('Build') {
      steps {
        sh 'mvn package'
      }
    }
    stage('Deploy') {
            environment {
               TOMCAT_HOME = '/opt/tomcat'
            }
            steps {
              sshagent(['deploy']){
            sh 'scp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/assgn_development/src/main/webapp/target/webapp.war ubuntu@13.55.100.146:/opt/tomcat/webapps'
              }
              
              }
        }
     
  }
    
  
}
