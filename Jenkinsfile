node{
    stage("clone"){
        git branch: 'main', url: 'https://github.com/ArunMagi/sample-html-app.git'
        sh "ls"
    }
    stage("docker image") {
        sh "docker build -t arunmagi/html ."
    }
    stage("docker hub") {
        sh "docker login -u arunmagi -p Arun@ak@99"
        sh "docker push arunmagi/html"
    }
    stage ("container"){
        sh "docker rm -f html-app"
        sh "docker run -d  --name html-app  -p 84:80 arunmagi/html"
    }
}
