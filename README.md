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
The notebook will use a dataset , download within the terminal of the jupyter env:
wget https://data.cityofnewyork.us/api/views/kku6-nxdu/rows.csv?accessType=DOWNLOAD
