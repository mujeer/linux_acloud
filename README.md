# some_code
just a shell script

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
