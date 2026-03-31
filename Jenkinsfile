    sh 'docker tag flask-app:latest $ECR_REPO:latest'
            }
        }

        stage('Push to ECR') {
            steps {
                sh '''
                aws ecr get-login-password --region $AWS_REGION | \
                docker login --username AWS --password-stdin $ECR_REPO
                docker push $ECR_REPO:latest
                '''
            }
        }

        stage('Deploy to ECS') {
            steps {
                echo 'Deploy using ECS Task Definition update'
            }
        }
    }
}