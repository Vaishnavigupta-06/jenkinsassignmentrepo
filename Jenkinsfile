pipeline
{
  agent any
  stages{
    stage('clone')
    {
      steps{
      git branch: 'testing', url: 'https://github.com/Rupali1520/jenkinsassignmentrepo.git'
      }}
    stage('build')
    {
      steps{
        sh '''javac test.java
             java test'''
      }
    }
  }
}
