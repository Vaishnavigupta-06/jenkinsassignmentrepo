pipeline
{
  agent any
  tools {
    maven 'maven-3.9.1' 
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
