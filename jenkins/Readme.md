docker build -t myjenkins .
docker build -t myjenkinsdata jenkins_data/.
docker run --name=jenkins-data myjenkinsdata
docker run -p 8080:8080 -p 50000:50000 --name=jenkins --volumes-from=jenkins-data -d myjenkins