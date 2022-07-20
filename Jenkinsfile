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
}     
