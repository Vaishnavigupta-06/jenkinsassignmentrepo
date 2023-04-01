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
                SSH_PRIVATE_KEY = credentials('-----BEGIN OPENSSH PRIVATE KEY-----
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
-----END OPENSSH PRIVATE KEY-----')
            }
            steps {
                sshagent(['ssh-private-key-id']) {
                    sh 'sudo cp /var/lib/jenkins/workspace/try_development/target/java-hello-world.war /opt/tomcat/webapps/'
                sh 'sudo /opt/tomcat/bin/shutdown.sh'
                sh 'sudo /opt/tomcat/bin/startup.sh'
                }
            }
        }
  }
    
  
}
