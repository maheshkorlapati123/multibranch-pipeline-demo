pipeline {

    agent {
        node {
            label 'TestNode'
        }
    }

    

    stages {
        
      

        stage('Code Checkout') {
            steps {
                checkout([
                    $class: 'GitSCM', 
                    userRemoteConfigs: [[url: 'https://github.com/maheshkorlapati123/multibranch-pipeline-demo.git']]
                ])
            }
        }

        stage(' Unit Testing') {
            steps {
                sh """
                echo "Running Unit Tests"
                """
            }
        }

        stage('Code Analysis') {
            steps {
                sh """
                echo "Running Code Analysis"
                """
            }
        }

        stage('Build Deploy Code') {
            when {
                branch 'develop'
            }
            steps {
                sh """
                echo "Building Artifact"
                """

                sh """
                echo "Deploying Code"
                """
            }
        }

    }   
}
