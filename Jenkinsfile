pipeline {
   agent any

   tools {
      // Install the Maven version configured as "M3" and add it to the path. Demo comment
      maven "maven"
      jdk "java"
                
   }

   stages {
      stage('Code Checkout') {
         steps {
            // Get some code from a GitHub repository
            git 'https://github.com/mallikach/tomcat.git'   
         }

      }
      
      
      stage('Code Testing') {
         steps {
           
            // To run Maven on a Windows agent, use
           bat "mvn test"
         }
      }
         
          stage('Code Build') {
         steps {
           
            // To run Maven on a Windows agent, use
           bat "mvn package"
         }

      }
      
      stage('Code Deploy') {
         steps {
        
            // To run Maven on a Windows agent, use
           bat label: '', script: 'copy /Y target\\mallikatest-1.0.war  C:\\Windows\\System32\\config\\systemprofile\\AppData\\Local\\Jenkins\\.jenkins\\workspace' 
            //E:\\apache-tomcat-9.0.16-windows-x64\\apache-tomcat-9.0.16\\webapps'
         }

      }
   }
}
