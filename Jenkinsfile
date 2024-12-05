pipeline{
   
    agent { label "vinod"}
    
    stages{
        
        stage("code"){
            steps{
                echo "This code is cloning "
                git url : "https://github.com/AniketNZade/django-notes-app.git/" ,branch:"main"
                echo "code is cloning successfully"
            }
        }
        stage("Build"){
            steps{
                echo "This is building the code"
                sh "docker build -t notes-app:latest ."
            }
        }
        stage("test"){
            steps{
                echo "This is testing the code"
            }
        }
        stage("Deploy"){
            steps{
                echo "This is Deploying the code"
                sh "docker run -d -p 8000:8000 notes-app:latest"
            }
        }
    }
}
        
   
