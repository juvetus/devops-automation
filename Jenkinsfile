pipeline {
    agent any
    tools{
        maven 'maven'
    }
    stages{
        stage('Build Maven'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/juvetus/devops-automation.git']]])
                sh 'mvn clean install'
            }
        }
//         stage('Build docker image'){
//             steps{
//                 script{
//                     sh 'docker build -t juvet/devops-integration .'
//                 }
//             }
//         }
//         stage('Push image to Hub'){
//             steps{
//                 script{
//                    withCredentials([string(credentialsId: 'dockerhub-pwd', variable: 'dockerhubpwd')]) {
//                    sh 'docker login -u juvet -p ${dockerhubpwd}'

// }
//                    sh 'docker push juvet/devops-integration'
//                 }
//             }
//         }
        // stage('Deploy to k8s'){
        //     steps{
        //         script{
        //             kubernetesDeploy (configs: 'deploymentservice.yaml',kubeconfigId: 'k8sconfigpwd')
        //         }
        //     }
        // }
    }
}