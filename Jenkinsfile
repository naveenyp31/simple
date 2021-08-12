pipeline{
    agent any
    tools{
        maven 'maven381'
    }
    stages{
          stage('Build'){
            steps{
                sh "mvn install -DskipTests"
            }
        }
        stage('Build'){
            steps{
                sh "mvn install -DskipTests"
            }
        }
        stage('Publish Junit test cases'){
            steps{
                sh 'mvn test'
            }
        }
        stage('uploading artifactory to nexus repo'){
            steps{
                nexusArtifactUploader artifacts: [[artifactId: 'addressbook', classifier: '', file: 'target/addressbook.war', type: 'war']], 
                credentialsId: 'nexus-artfact', 
                groupId: 'com.Nandihal', 
                nexusUrl: '15.206.116.125:8081', 
                nexusVersion: 'nexus3', 
                protocol: 'http', 
                repository: 'release', 
                version: '2.0'
            }
        }
    }
}