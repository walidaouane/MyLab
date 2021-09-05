pipeline{
    //Directives
    agent any
    tools {
        maven 'maven'
    }
    environment {
        ArtifactId = readMavenPom().getArtifactId()
        Version =  readMavenPom().getVersion()
        Name = readMavenPom().getName()
        GroupID = readMavenPom().getGroupId()
    }

    stages {
        // Specify various stage with in stages

        // stage 1. Build
        stage ('Build'){
            steps {
                sh 'mvn clean install package'
            }
        }

        // Stage2 : Testing
        stage ('Test'){
            steps {
                echo ' testing......'

            }
        }

        // Stage3 : Publish the artifacts to Nexus
        // stage ('Publish to Nexus'){
        //     steps {
        //         nexusArtifactUploader artifacts: 
        //         [[artifactId: 'VinayDevOpsLab', 
        //         classifier: '', 
        //         file: 'target/VinayDevOpsLab-0.0.3-SNAPSHOT.war', 
        //         type: 'war']], 
        //         credentialsId: 'f01f6811-e0f9-4bac-a5d5-d9d5511793fa', 
        //         groupId: 'com.vinaysdevopslab', 
        //         nexusUrl: '35.180.190.60:8081', 
        //         nexusVersion: 'nexus3', 
        //         protocol: 'http', 
        //         repository: 'VinaysDevOpsLab-SNAPSHOT', 
        //         version: '0.0.3-SNAPSHOT'
        //     }
        // }

        // Stage4 : ¨Print some information
        stage ('Print Environment variables'){
            steps {
                echo "Artifact Id is '${ArtifactId}'"
                echo "Version is '${Version}'"
                echo "GroupID is '{}'"
                echo "Name is '${Name}'"

            }
        }

        // Stage5 : Deploying
        stage ('Deploy'){
            steps {
                echo ' deploying......'

            }
        }

        // Stage6 : Publish the source code to Sonarqube
        // stage ('Sonarqube Analysis'){
        //     steps {
        //         echo ' Source code published to Sonarqube for SCA......'
        //         withSonarQubeEnv('sonarqube'){ // You can override the credential to be used
        //              sh 'mvn sonar:sonar'
        //         }

        //     }
        // }

        
        
    }

}