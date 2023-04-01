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
    stage('deploy'){
      steps{
        
        #sshagent(['hello']) {
    sh 'scp -o StrictHostKeyChecking=no /target/java-hello-world.war knoldus@127.0.0.1:/opt/tomcat/webapps'
#}
      }
    }
  }
    
  
}
