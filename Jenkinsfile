pipeline {
  agent any
  tools {
    maven 'maven3'
  }
  stages {
    stage('Merge release to main') {
      steps {
        script {
          def releaseBranch = 'release'
          def mainBranch = 'main'
          git branch: releaseBranch, url: 'https://github.com/PandeeswariSubbaiya/Branch_Strategy.git' 
        }
      }
    }
stage('Build') {
            steps {
              script {
                def mvnHome = tool name: 'maven3', type: 'maven'
                //sh "${mvnHome}/bin/mvn clean package"
                sh 'mvn clean install'
              }
            }
        }
    }
}
