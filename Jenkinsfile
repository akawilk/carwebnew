node ('Ubuntu-Appserver-3120')
{

def Testing
stage('Cloning Git')
{
    /* Let's make sure we have the repository cloned to our workspace */
    checkout scm
}

stage('Build-and-Tag')
{
    /* This builds the actual image;
         * This is synonymous to docker build on the command line */
    docker.build('akawilk/car_webnew_repo')
}

stage('Post-to-dockerhub')
{
    docker.withRegistry('https://registry.hub.docker.com', 'dockerhub-creds-2') {
        echo 'hello'
    }
}

stage('Deploy')
{
     sh "docker-compose down"
}    sh "docker-compose up -d"

}
