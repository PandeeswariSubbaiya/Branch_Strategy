pipeline {
    agent any
    tools { 
        maven 'maven3' 
           }
    environment{
      def BRANCH_NAME ='GIT_BRANCH'
  }
stages {
      stage('GIT checkout') {
           steps {
               script{
                   if (env.GIT_BRANCH.contains('main')) {
                echo 'Hello from main branch'
                git branch: 'main', url: 'https://github.com/PandeeswariSubbaiya/Branch_Strategy.git'
                }
               else {
    //        sh echo 'Hello from ${env.BRANCH_NAME} branch!'"
     //              echo 'Hello from ${env.BRANCH_NAME} branch!
                   echo "Run this stage only if the branch is not main"
                  git branch: 'release1', url: 'https://github.com/PandeeswariSubbaiya/Branch_Strategy.git' 
               }
               }
          }
        }
    stage('Merge release to main') {
                        steps {
                            script {
                                sh "git checkout main"
                                sh "git merge --no-ff --allow-unrelated-histories release1"
                                    }
                                }
                             }
     stage('Push Changes') {
            steps {
                // Push changes to the Git repository
                withCredentials([usernamePassword(credentialsId: 'PandeeswariSubbaiya', usernameVariable: 'PandeeswariSubbaiya', passwordVariable: 'Subbaiya@08')]) {
                    sh "git config user.name 'Pandeeswari'"
                    sh "git config user.email 'Pandeeswari318@gmail.com'"
                    sh "git push origin main"
                }
            }
        }
     }
  }
