//Change build display name
currentBuild.displayName = "petclinic-#"+currentBuild.number

//Environment variables
env.DOCKER_HOST = 'tcp://192.168.99.100:2376'
env.DOCKER_CERT_PATH = 'C:/Users/ekant/.docker/machine/machines/default'
env.DOCKER_MACHINE_NAME = 'default'
env.DOCKER_TLS_VERIFY = '1'
env.DOCKER_TOOLBOX_INSTALL_PATH = 'C:/Program Files/Docker Toolbox'
env.DOCKER_TAG = getDockerTag()
env.DOCKER_REGISTRY = 'tany2020/pipeline'

pipeline{
    agent any
    //Adding maven distribution to PATH variable
    environment{
        PATH = "T:/Tanya/Softwares/apache-maven-3.6.3-bin/apache-maven-3.6.3/bin;$DOCKER_TOOLBOX_INSTALL_PATH:$PATH"
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
        stage("Docker build-push"){
            steps{
                 powershell label: '', script: 'docker --version'
                 //powershell label: '', script: 'DOCKER_TOOLBOX_INSTALL_PATH/docker build -t $DOCKER_REGISTRY:$DOCKER_TAG .'
                 //powershell label: '', script: 'DOCKER_TOOLBOX_INSTALL_PATH/docker images'
                
            }
        }
    }
}
def getDockerTag(){
    def tag = powershell label: '', script: 'git rev-parse HEAD', returnStdout = true
    return tag
    }
