
pipeline{
    
    agent any
    
    stages{
        stage("checkout"){
        steps
        {
            git branch:'main', url:'https://github.com/ohyesboy/course3-jenkins-gs-spring-petclinic.git'
        }
        }
        
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
