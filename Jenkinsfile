    node{
        stage ('git checkout'){
            git credentialsId: 'd2c8f2e9-60ec-4d0e-8976-654181b2ca2c', url: 'https://github.com/GSalah/Spring_CD.git'
        }
        stage ('mvn clean') {
            def mvnHome = tool name: 'maven 11', type: 'maven'
            def mvnCMD = "${mvnHome}/bin/mvn"
            sh "${mvnCMD}  clean"
        }
        
        stage ('mvn package') {
            def mvnHome = tool name: 'maven 11', type: 'maven'
            def mvnCMD = "${mvnHome}/bin/mvn"
            sh "${mvnCMD}  package"
        }
        stage ('Build Docker Image'){
            sh 'mvn docker:build'
        }
    }
