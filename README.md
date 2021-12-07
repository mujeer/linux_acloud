# some_code
just a shell script pole scm

you need to pass the valued 

![image](https://user-images.githubusercontent.com/15226709/144150237-7760f49e-7459-4794-a922-bfb955563507.png)
![image](https://user-images.githubusercontent.com/15226709/144150306-a46ab1bc-9268-48fe-968b-2803c1b71f7c.png)
![image](https://user-images.githubusercontent.com/15226709/144150673-317c14f9-90ad-4271-bec1-0e0e3231a949.png)
![image](https://user-images.githubusercontent.com/15226709/144150917-7f4471b5-a80c-4267-9ea1-2ecb7a40702f.png)



************** Hello World *************************

pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
    }
}
************** Git Checkout ************************
pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            } 
        }    
        
        stage('Git Checkout') {
            steps {
                git 'https://github.com/mujeer/pipeline_shell_script.git'
            }
        }
    }
}
************* Git Run Shell Commands pipeline syntax: sh: shell script***************
pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
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
                ./testscript.sh'''
            }  
        }
    }
}
############### ArchivArtifacts ######################
pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
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
###################################################

