
pipeline{
    
    agent any
    
    stages{

        
        stage("build"){
        steps
        {
            sh "./mvnw package"
        }
        }
        
        stage("capture"){
        steps
        {
            archiveArtifacts '**/target/*.jar'
        }
        }
    
    }
    
    post{
        always
        {
            emailext body: "You got the  message at ${BUILD_URL}\n${currentBuild.absoluteUrl}",
                recipientProviders: [developers()],
                subject: "Hi developers: ${currentBuild.currentResult}",
                to: 'dev@foo.com'
        }
     
    }
   
    
}
