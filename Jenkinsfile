pipeline {
    agent any
    triggers {
        pollSCM ignorePostCommitHooks: true, scmpoll_spec: '*/1 * * * *'
        }
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World changed Hello Again hello  done'
            } 
        }    
        
        stage('Git Checkout') {
            steps {
                git 'https://github.com/mujeer/pipeline_shell_script.git'
            }
          }
        stage('Run the Shell Script') {
            steps {
                sh '''chmod +x testscript.sh 
                ./testscript.sh > testscript.txt'''
            }  
        }
        stage('ArchivArtifacts') {
            steps {
                archiveArtifacts artifacts: 'testscript.txt', followSymlinks: false
            }  
        }
    }
}
