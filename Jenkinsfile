@Library('Shared')_
pipeline{
    agent { label 'vinod'}
    
    stages{
        stage("Code clone"){
            steps{
                sh "whoami"
            clone("https://github.com/AniketNZade/django-notes-app.git","main")
            }
        }
        stage("Code Build"){
            steps{
            dockerbuild("notes-app","latest")
            }
        }
        stage("Push to DockerHub"){
            steps{
                dockerpush("9c90dc33-e63e-4b26-825a-dea97fe4f246","notes-app","latest")
            }
        }
        stage("Deploy"){
            steps{
                deploy("docker compose down && docker compose up -d --build")
            }
        }
        
    }
}
        
   
