# LoanPrediction
This project is based on the Analytics Vidhya Challenge for the loan prediction problem



## create conda env in the project folder

```
conda create -p <env name> python==3.xx -y 
```
-p in this line will make sure the conda environment is created in the project folder, as our command propmt is locating this folder currently


## activate conda using following command
```
conda activate <env name>/
```
the slash will enable the command prompt to look inside the env folder


### Crete requirements.txt and list all the package names

```
pip install -r requirements.txt

```

### Other Commands
Mention the venv_test name in the gitignore file so that git will not track this folder


### Git Commands

- [git status] will show the status of the git
- [git add filename or git add .] will add all the files to git 
- [git status]  to check status 
- [git log] to check all versiosn
- [git commit -m "message"] commit with the message
- [git push origin main] pushes the changes to git hub 


### Heroku Requirements
1. Heroku_Email
2. Heroku_API_kEy
3. Herroku_App_name


## Docker Based Commands

Build Docker Image

```
docker build -t <image_name>:<tagname> . 
```

> Note : Image name should always be in caps off 

to list docker images 

```
docker images
```

Run Docker Image

```
docker run -p 5000:5000 -e PORT=5000 <Image_ID>

```

Check Running containers in docker

```
docker ps

```

Stop Docker Container

```
docker stop <container ID>

```


## Create Docker file

FROM python:3.7   #calls for for an OS that has Python 3.7  
COPY . /app       # copy all the files from our directory to a new directory called app in the OS
WORKDIR /app      # set app as the working directory
RUN pip install -r requirements.txt    # install all the required packages to the OS 
EXPOSE $PORT     # Assign the port that is exposed 
CMD gunicorn --workers =4 --bind 0.0.0.0:$PORT app:app #gunicorn package will assign workers and expose the port app refers to app.py and other app refers to the object name inside app.py 