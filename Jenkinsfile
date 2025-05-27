pipeline{
    agent any
    tools{
        maven 'Maven'
    }
    stages{
        stage("Test"){
            steps{
                // maven test
                echo "Testing Maven........"
                sh'''
                mvn test
                '''
            }
        }
        stage("Build"){
            steps{
                // maven Package
                echo "Building Maven Package........"
                sh '''
                mvn package
                '''
                
            }
        }
        stage("Deploy on Prod"){
            steps{
                // Deploy on Container - Plugin
                echo "Deploying on Prod........"
                deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'tomcatserver', path: '', url: 'http://43.205.116.148:8080')], contextPath: '/app', war: '**/*.war'
                
            }
        }
    }
    post{
        always{
            echo "========Always!========"
        }
        success{
            echo "========Pipeline Executed Successfully! ========"
        }
        failure{
            echo "========Pipeline Execution Failed!========"
        }
    }
}
