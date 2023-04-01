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
               deploy adapters: [tomcat9(credentialsId: 'admin', path: '', url: 'http://0.0.0.0:8080')], contextPath: null, onFailure: false, war: '**/*.war'
            }
        }
     
  }
    
  
}
