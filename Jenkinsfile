pipeline {

  agent { label 'jenkins' }

  stages {

    stage('Checkout Source') {
      steps {
        git url:'https://github.com/mdv-terraform-modules/playjenkins.git', branch:'master'
      }
    }

    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "nginx.yaml", kubeconfigId: "kubeconfig")
        }
      }
    }

  }

}
