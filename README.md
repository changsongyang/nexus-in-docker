# nexus-in-docker
Using docker-compose to deploy Nexus in docker

## how to use

* run ``` docker-compose up -d ```

* wait a few seconds and open your browser , and visit http://localhost:8081 , the account is admin , and password is admin123

### deploy repositories

* first of all , we need sign in as admin user , and than create a repository . 

![1.jpg](https://github.com/liumapp/nexus-in-docker/blob/master/pic/1.jpg)

* choice maven2 repository

![2.jpg](https://github.com/liumapp/nexus-in-docker/blob/master/pic/2.jpg)

* plz pay attention , we need set repository's name and version policy and deployment policy.

![3.jpg](https://github.com/liumapp/nexus-in-docker/blob/master/pic/3.jpg)

* than , we need to create a user named liumapp (or some name else you like )

![4.jpg](https://github.com/liumapp/nexus-in-docker/blob/master/pic/4.jpg)

* set user's property

![5.jpg](https://github.com/liumapp/nexus-in-docker/blob/master/pic/5.jpg)

* using commond : 

		mvn deploy:deploy-file -DgroupId=com.liumapp.convert.html -DartifactId=convert-html-to-pdf -Dversion=v1.0.0 -Dpackaging=jar -Dfile=./target/convert-html-to-pdf-v1.0.0.jar -Durl=http://127.0.0.1:8081/repository/liumapp/ -DrepositoryId=liumapp

	to deploy your maven project .		


![6.jpg](https://github.com/liumapp/nexus-in-docker/blob/master/pic/6.jpg)