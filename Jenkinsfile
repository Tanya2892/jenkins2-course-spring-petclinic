pipeline{
    agent any
    environment{
        PATH = "T:/Tanya/Softwares/apache-maven-3.6.3-bin/apache-maven-3.6.3/bin:$PATH"
    }
    stages{
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
