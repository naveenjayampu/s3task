pipeline
{
    agent any 
    
    stages
    {
     
     stage ('compile code')
     {
         steps
         {
             sh 'mvn clean install'
         }  
     }
        stage ('find my binary')
     {
         steps
         {
             sh 'find / -name *.war'
         }
     }
        stage ('deploy')
     {
         steps
         {
             sh 'cp -R /root/.jenkins/workspace/s3task/target/* /opt/apache-tomcat-8.5.3/webapps'
         }
    }
         }
     post {
        always {
            slackSend channel: '#developer',                
                message: "Result : ${currentBuild.currentResult}\n Job : ${env.JOB_NAME}\n buildno : ${env.BUILD_NUMBER} \n More info at: ${env.BUILD_URL}"
        }
    }
}
