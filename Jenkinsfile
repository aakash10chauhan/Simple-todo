pipeline {
    agent any

    environment {
        BKT_NAME = "jenkins-btk-aws-deploy-s3"
    }

    stages {

        stage('Git Clone') {
            steps {
                echo 'Cloning repo...'
                git branch: 'main', url: 'https://github.com/AakashRanjeetChauhan/Simple-todo.git'
            }
        }

        stage('Check S3 Bucket') {
            steps {
                echo 'Checking S3 bucket...'
                sh '''
                if aws s3 ls s3://${BKT_NAME}; then
                    echo "Bucket already exists"
                else
                    echo "Creating bucket..."
                    aws s3 mb s3://${BKT_NAME}
                fi
                '''
            }
        }

        stage('Deploy to S3') {
            steps {
                echo 'Deploying files to S3...'
                sh '''
                aws s3 sync . s3://${BKT_NAME}
                '''
            }
        }
    }
}

