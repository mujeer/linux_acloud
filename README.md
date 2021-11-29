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

