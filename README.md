This project contains a jupyter and Zeppelin notebook with personal playground, kitchensink code.
USed for Spark icm Scala, Python and Angular (in Zeppelin).
Most code is in the Zeppelin notebook (note.json)

# To run a jupyter notebook on Docker

Using Scala and spark using jupyter locally on Mac using docker
Some background info: https://hub.docker.com/r/jupyter/all-spark-notebook/

To start (docker should be installed first):
```
docker run -it --rm -p 8888:8888 jupyter/all-spark-notebook

Open the jupyter url as given.
Create a notebook with Spark scala for example
Open a terminal session within the jupyter environment and use these initial steps to push your code to git:

git init
git add ScalaSpark.ipynb
git config --global user.email "email"
git config --global user.name "Name"
git commit -m "first commit"
<create a repo in git and use in next steps>
git remote add origin https://github.com/yourgitaccount/<yourrepo>.git
git push -u origin master

Next time when using the docker image , you can just do the add,commit and push steps

```
This notebook will use a dataset , download within the terminal of the jupyter env:
wget https://data.cityofnewyork.us/api/views/kku6-nxdu/rows.csv?accessType=DOWNLOAD

# To run a Zeppelin notebook on Docker. It uses spark 2.1.1 at this moment

We will use this Zeppelin with Spark environment:
```
docker pull dylanmei/zeppelin
docker run --rm -p 8080:8080 dylanmei/zeppelin

localhost:8080 will give access to Zeppelin.
```

The initial test notebook was copied from this location and later changed using different sources:
```
This tutorial mentions a notebook to load in:
https://hortonworks.com/tutorial/learning-spark-sql-with-zeppelin/

This is the notebook url which can be loaded in from  Zeppelin's mainpage (import notebook option)
https://raw.githubusercontent.com/hortonworks-gallery/zeppelin-notebooks/hdp-2.6/2CJW53M52/note.json
```

After making changes to the notebook we want to save it to Git.
To use the previously created Git repo on thos Docker images we will:
```
Install Git on the Docker image: 
Log on running Docker env (docker ps) using: docker exec -it <container> bash (check container user docker ps)
apt-get update
apt-get install git
```

Clone your personal repo to the docker env:
```
cd /usr/zeppelin
git clone https://github.com/yourgitaccount/<yourrepo>.git
```

Add your changes in the notebook to the repo and push:
```
cd <therepo> (e.g. cp /usr/zeppelin/notebook/2CSGRDE7D/note.json /usr/zeppelin/sparkscala
cd /usr/zeppelin/sparkscala
git add note.json
git commit -m 'intial commit zeppelin' 
git push
```
