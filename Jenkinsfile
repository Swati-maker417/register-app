pipeline{
  agent { label 'jenkins-agent'}
  tools{
        jdk 'Java17'
        maven 'Maven3'
        }
  stages{
    stage("clean the workspace"){
      steps{
        cleanWs()
      }
    }
    stage("checking out form scm"){
      steps{
        git branch: 'main', credentialID: 'github', git url:"https://github.com/Ashfaque-9x/register-app.git"
      }
    }
    stage("Build application"){
      steps{
        sh 'mvn clean package'
      }
    }

  stage("test the application"){
    steps{
      sh 'mvn test'
    }
  }
}
  
