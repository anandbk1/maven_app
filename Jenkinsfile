
node {
   stage('Code checkout') { // for display purposes
      // Get some code from a GitHub repository
   checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'SATYA', url: 'https://github.com/itrainspartans/maven_app.git']]]) 
   stage('Build') {
     withMaven(jdk: 'java', maven: 'Maven')  {
      sh 'mvn clean compile'
     } 
   }
   stage('Test') {
   withMaven(jdk: 'java', maven: 'Maven') {
      sh 'mvn test'
     }  
   }
   stage('Sonar CodeAnalysis') {
     withSonarQubeEnv('itrainspartans') {
       sh 'mvn clean verify sonar:sonar'
          }

    }
   stage('Package') {
    withMaven(jdk: 'java', maven: 'Maven') {
      sh 'mvn package'
     }  
   }
   
   
   stage('Artifactory') {
     
   }
   
   stage('Docker Build') {
     
   }
   
   stage('Deploy to Dev') {
     
   }
   stage('Deploy to Stage') {
     
   }
   stage('Deploy to Prod') {
     
   }
}

