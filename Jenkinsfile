 pipeline{
     agent any
     triggers {

             cron('30 8 * * 1-5')
         }
     stages{
     stage('Java Version') {
                 steps {
                     sh 'java --version'
                 }
             }
       stage('Gradle version')
              {
            steps {
                		sh './gradlew --version'
            }
          }
         stage('build')
         {
       steps {
           		sh './gradlew build'
       }
     }
      stage('Test Run')
         {
       steps {
           		sh './gradlew clean test'
           		sh './gradlew allureReport'
           		sh './gradlew allureServe'
       }

     }
     }
      post{
              always{
                  slackSend channel:'slacknotification',message:"find status of pipeline ${env.JOB_NAME} ${env.BUILD_NUMBER} ${env.BUILD_URL} "
              }
          }
 }