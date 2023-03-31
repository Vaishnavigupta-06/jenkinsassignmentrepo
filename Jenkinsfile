pipeline
{
  agent any
  stages{
    stage('clone')
    {
      steps{
      git branch: 'prod', url: 'https://github.com/Rupali1520/jenkinsassignmentrepo.git'
      }}
    stage('build')
    {
      steps{
        sh '''javac prod.java
             java prod'''
      }
    }
  }
}
