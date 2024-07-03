pipeline {
    agent any

    stages {
        stage('Checkout SCM') {
            steps {
                git url: 'https://github.com/mandelasasidhar/Azure-Terraform.git', branch: 'master'
            }
        }
        stage('Tool Install') {
            steps {
                // Install and use the required tools
                // For example, terraform installation
                tool name: 'Terraform', type: 'TerraformInstallation'
            }
        }
        stage('Terraform Init') {
            steps {
                ansiColor('xterm') {
                    script {
                        // Initialize Terraform
                        sh 'terraform init'
                    }
                }
            }
        }
        stage('Terraform Validate') {
            steps {
                ansiColor('xterm') {
                    script {
                        // Validate Terraform configuration
                        sh 'terraform validate'
                    }
                }
            }
        }
        stage('Terraform Plan') {
            steps {
                ansiColor('xterm') {
                    script {
                        // Plan Terraform changes
                        sh 'terraform plan'
                    }
                }
            }
        }
        stage('Terraform Apply') {
            steps {
                ansiColor('xterm') {
                    script {
                        // Apply Terraform changes
                        sh 'terraform apply -auto-approve'
                    }
                }
            }
        }
    }
}
