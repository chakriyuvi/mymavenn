node('built-in')
{
 stage('ContinuousDownload')
  {
    git 'https://github.com/chakriyuvi/mymavenn.git'
  }
      stage('ContinuousBuild')
     {
       sh 'mvn package'
     }
       stage('ContinuousDeployment')
       {
        deploy adapters: [tomcat9(credentialsId: '45e382ec-3c09-4198-8735-9d561acfb075', path: '', url: 'http://172.31.86.173:8080')], contextPath: 'testapp', war: '**/*.war'
       }
           stage('ContinuousTesting')
          {
           git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
           sh 'java -jar /home/ubuntu/.jenkins/workspace/scriptedpipeline1/testing.jar'
          }
            stage('ContinuousDeploy')
             {
                input message: 'Need approvals of the DM!', submitter: 'chakri' 
               deploy adapters: [tomcat9(credentialsId: '45e382ec-3c09-4198-8735-9d561acfb075', path: '', url: 'http://172.31.80.134:8080')], contextPath: 'prodapp', war: '**/*.war'
             }
}
