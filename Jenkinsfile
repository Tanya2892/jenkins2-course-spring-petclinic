pipeline{
    agent any
    environment{
        PATH = "T:/Tanya/Softwares/apache-maven-3.6.3-bin/apache-maven-3.6.3/bin:$PATH"
    }
    stages{
        stage("checkout"){
            steps{
                 git 'https://github.com/Tanya2892/jenkins2-course-spring-petclinic.git'
                 }
                 
        }
        stage("package"){
            steps{
                 bat label: 'package', script: 'mvn clean package'
                 }
        }
          stage("archive"){
            steps{
                 archiveArtifacts "target/*.?ar"
                 }
        }
    }
}
