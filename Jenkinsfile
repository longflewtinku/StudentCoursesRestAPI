pipeline {
    agent { label 'OPENJDK-11-JDK' }
    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage('learning') {
            steps {
                git url: 'https://github.com/DevProjectsForDevOps/StudentCoursesRestAPI.git', 
                    branch: 'master'
            }
        }    
        stage('Example Build') {
            steps {
                sh """docker image build -t one:1.0 .
                      docker image tag one:1.0 longflew/laxmitinku:1.0
                      docker image push longflew/laxmitinku:1.0
                      docker container run -d -P longflew/laxmitinku:1.0"""
                     
            }
        }
    }
}