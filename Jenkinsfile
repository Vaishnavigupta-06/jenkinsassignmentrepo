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
        sh 'mvn clean install'
      }
    }
     stage('Deploy') {
            environment {
               TOMCAT_HOME = '/opt/tomcat'
            }
            steps {
        script {
          def warFile = findFiles(glob: env.WAR_PATTERN)[0]
          def tomcat = Tomcat.httpRequest(env.TOMCAT_URL)
          tomcat.auth.basic('admin', credentials('admin'))
          tomcat.multipartUpload {
            file(warFile)
            field 'path', env.CONTEXT_PATH
          }
        }
        }
   
    
  }
    
  
}
