# some_code
just a shell script

you need to pass the valued 

![image](https://user-images.githubusercontent.com/15226709/144150237-7760f49e-7459-4794-a922-bfb955563507.png)


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
************* Git Run Shell Commands ***************

