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
        sh 'mvn clean package'
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
  }
    
  
}
