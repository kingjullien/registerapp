pipeline{
    agent { label 'Jenkins-Agent'}
    tools {
        jdk 'java17'
        maven 'Maven3'
    }
    stages{
        stage("Cleanup Workspace"){
                steps {
                cleanws()
                }
            }
        stage("Checkout from SCM"){
            steps {
                git branch: 'main', 'credentailsID': 'github', url: 'https://github.com/kingjullien/registerapp'
            }
        }
        stage("Build Application"){
            steps {
                sh "mvn clean package"
            }
        }
        stage("Test Application") {
            steps{
                sh "mvn test"
            }
        } 
    }