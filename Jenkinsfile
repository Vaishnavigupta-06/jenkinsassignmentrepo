pipeline
{
  agent any
  stages{
    stage('clone')
    {
      steps{
      git branch: 'production', url: 'https://github.com/Rupali1520/jenkinsassignmentrepo.git'
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
