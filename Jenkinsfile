node{
    
    stage('SCM Checkout')
    {
        url: 'https://github.com/rahul26ur/TestProject.git'
    }
    stage ('Compile Stage') 
    {
        
        withMaven(maven : 'apache-maven-3.6.1') {
        bat'mvn clean compile'
        }
    }
    stage('Run Docker Compose File')
    {
        
        sh 'sudo docker-compose build'
        sh 'sudo docker-compose up -d'
    }
    /*
    stage('PUSH image to Docker Hub')
    {
        withCredentials([string(credentialsId: 'DockerHubPassword', variable: 'DHPWD')]) 
        {
            sh "docker login -u vardhanns -p ${DHPWD}"
        }
        sh 'docker push vardhanns/phpmysql_app'
    }*/
}
