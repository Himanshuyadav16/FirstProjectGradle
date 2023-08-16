 pipeline{
     agent any
     stages{
         stage('build')
         {
       steps {
           		sh './gradlew build'
           		echo "hello world"
       }
     }
      stage('Test Run')
         {
       steps {
           		sh './gradlew clean test'
       }
     }
     }
 }