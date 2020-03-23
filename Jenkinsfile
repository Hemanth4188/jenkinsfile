pipeline {
	agent any
	stages {
	stage ('SCm checkout') {
		steps {
			script {		
 	
           url 'https://github.com/Hemanth4188/jenkinsfile.git'
		}
	}
	}

    stages {
	stage ('build') {
		steps {
			script {		
 	
             sh 'mvn clean package'
		}
	}
	}
		
	stages {
	stage ('Junit test') {
		steps {
			script {		
 	
            junit '/target/test-reports/*.xml'
		}
	}
	}
  post
    {
         success
        {
            script
            {
            
		    mail to: 'bojanapuhemant8@gmail.com',
                     subject: "Build + Condition Pass",
                     body: "Build got success check status @ ${env.BUILD_URL}"
                
            }
	}
        
          failure
	   {
		   script
		   {
                mail to: 'bojanapuhemant8@gmail.com',
                     subject: "Build fail + Condition Pass",
                     body: "Build got success check status @ ${env.BUILD_URL}"
                 
            }
        }
    }
                            
        }
    
		
	    }

	}

