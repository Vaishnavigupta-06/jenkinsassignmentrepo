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
    }
    stage('email')
    {
      steps{
        emailext body: 'hello', subject: 'jenkins build notification', to: 'rupali.gupta@knoldus.com'
      }
    }
  }
}
