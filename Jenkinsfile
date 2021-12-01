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
    }
}
