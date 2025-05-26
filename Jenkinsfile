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
        stage("Deploy on Test"){
            steps{
                // Deploy on Container - Plugin
                deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'tomcatserver', path: '', url: 'http://65.1.109.107:8080')], contextPath: '/app', war: '**/*.war'
                echo "Deploying on Test........"
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
