//Change build display name
currentBuild.displayName = "petclinic-#"+currentBuild.number
pipeline{
    agent any
    //Adding maven distribution to PATH variable
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
