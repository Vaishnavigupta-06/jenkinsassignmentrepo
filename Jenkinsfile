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
    stage('Deploy') {
            environment {
                SSH_PRIVATE_KEY = credentials('2efcdd8f-1e19-488b-90ef-7ad8482783f1')
            }
            steps {
                sshagent(['2efcdd8f-1e19-488b-90ef-7ad8482783f1']) {
                    sh 'sudo cp /var/lib/jenkins/workspace/try_development/target/java-hello-world.war /opt/tomcat/webapps/'
                sh 'sudo /opt/tomcat/bin/shutdown.sh'
                sh 'sudo /opt/tomcat/bin/startup.sh'
                }
            }
        }
  }
    
  
}
