pipeline{
    agent any
    tools{
        maven 'Maven'
    }
    stages{
        stage("Test"){
            steps{
                // maven test
                sh'''
                mvn test
                '''
                echo "Testing........"
            }
        }
        stage("Build"){
            steps{
                // maven Package
                sh '''
                mvn package
                '''
                echo "Building........"
            }
        }
        stage("Deploy on Prod"){
            steps{
                // Deploy on Container - Plugin
                deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'tomcatserver', path: '', url: 'http://13.126.137.77:8081')], contextPath: '/app', war: '**/*.war'
                echo "Deploying on Prod........"
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
