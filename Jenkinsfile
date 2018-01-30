node("docker") {
    docker.withRegistry('https://hub.docker.com/', 'DockerID') {
    
        git url: "https://github.com/fidelitee/python-app.git", credentialsId: 'GithubID'
    
        sh "git rev-parse HEAD > .git/commit-id"
        def commit_id = readFile('.git/commit-id').trim()
        println commit_id
    
        stage "build"
        def app = docker.build "manee2k6/fidelitee:007"
    
        stage "publish"
        app.push 'master'
        app.push "${commit_id}"
    }
}
