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
  }
    post{
        
        
          
        always{
        
        
          
            mail to: "rupali.gupta@knoldus.com",
        
        
          
            subject: "Build result",
        
        
          
            body: "success"
        
        
          
        }
        
        
              }
  
}
