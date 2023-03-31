pipeline
{
  agent any
  stages{
    stage('clone')
    {
      steps{
      git branch: 'development', url: 'https://github.com/Rupali1520/jenkinsassignmentrepo.git'
      }}
    stage('build')
    {
      steps{
        sh '''javac dev.java
             java dev'''
      }
    }}
    post{
        
        
          
        always{
        
        
          
            mail to: "rupali.gupta@knoldus.com",
        
        
          
            subject: "Build result",
        
        
          
            body: "success"
        
        
          
        }
        
        
              }
  
}
