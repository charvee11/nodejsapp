def latestTag = 'UnKnown'
pipeline {
    
     environment {
        BRANCH_NAME = "vahana-to-vconnect"
        MAJOR_VERSION = "1"
        MINOR_VERSION = "0"
        GIT_REPO = "http://devops.decimaltech.net/charvee.punia/vahana-tpgweb-vconnect.git"
        GIT_USER = "charvee.punia"
        GIT_PASS = "Sarita#1964"
    //    MyID     = "464b868b-2193-4431-9fb1-758c51c476a9"
                    
}
   tools {nodejs "node"}     
   agent any
    stages {
        stage('Build') {
            steps {
                  sh 'echo "machine http://devops.decimaltech.net/charvee.punia/vahana-tpgweb-vconnect.git" >> $WORKSPACE/.netrc'
                  sh 'echo "login $GIT_USER" >> $WORKSPACE/.netrc'
                  sh 'echo "password $GIT_PASS" >> $WORKSPACE/.netrc'
                  sh 'echo "protocol http" >> $WORKSPACE/.netrc'
                  sh 'chmod 600 $WORKSPACE/.netrc'
        //        sh "git config --global user.name 'charvee.punia'"
         //       sh "git config --global user.email 'charvee.punia@decimal.co.in'" 

         //       withCredentials([[$class: 'UsernamePasswordMultiBinding', credentialsId: 'gitlab_external', usernameVariable: 'GIT_USER', passwordVariable: 'GIT_PASS']]) 
         //       {
 //             sh 'git clone -b $BRANCH_NAME $GIT_REPO'
                sh 'echo Code Building started......'
                sh 'ls'
                sh 'chmod a+rwx build.sh'
                sh './build.sh'
                sh 'chmod a+rwx git_tagging.sh'
                sh './git_tagging.sh'
                echo 'code building done'
           //        }            
}
        }
 //        stage('Prepare artifacts') {
 //            steps {
 //                script{
 //                sh 'ls'
 //              sh 'git fetch --tags'
 //              sh 'zip $(git describe --abbrev=0 --tags) -r ./'
 //                archiveArtifacts '**'
 //             sh 'ls'
 //              }
 //
 //         }
 //       }
     }  
}    

