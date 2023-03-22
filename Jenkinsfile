pipeline {
  agent any
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
  }
}
