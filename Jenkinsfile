pipeline {
  agent any
  environment {
    AWS_ACCESS_KEY_ID = credentials('accesskeyid')
    AWS_ACCESS_SECRET_KEY = credentials('accesskey')
  }
  stages {
    stage('Checkout the code') {
      steps {
        script {
          git branch: 'main', credentialsId: 'githubId', url: 'https://github.com/astridmuriel/devops-lightfeather'

          sh 'ls -l'
        }
      }
    }

    stage('Terraform init') {
      steps {
        sh 'terraform init -backend-config=backend/devops.tf'
      }
    }

    stage('Terraform plan') {
      steps {
        sh 'terraform plan -var-file vars/devops.tfvars'
      }
    }

    stage('Terraform apply') {
      steps {
        sh 'terraform apply -var-file vars/devops.tfvars -auto-approve'
      }
    }
  }
}