pipeline
{
  agent any
  environment
  { 
    PATH="/opt/apache-maven-3.6.3/bin:$PATH"
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
                sh 'cp target/java-hello-world.war $TOMCAT_HOME/webapps/'
                sh '$TOMCAT_HOME/bin/shutdown.sh'
                sh '$TOMCAT_HOME/bin/startup.sh'
            }
        }
  }
    
  
}
