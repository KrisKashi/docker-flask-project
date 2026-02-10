Docker Flask Project with CI/CD pipeline 

## What I built

Dockerized container that hosts a webapp using flask, with a CI/CD pipeline using Github actions 
 
 Function : Flask app displays simple website with a print statement to show that its working, when code for this repo is pushed to github the docker image is automatically created.

# Next steps
- Learn how to use flask to host more complex web pages instead of simple text / multi- page websites 
- Host the flask container on an AWS EC2 instead of locally 

# Tech Requirements

Docker,Python,Flask, Github actions  

# What I learned

## Github actions 

- Uses same Yaml file format as Azure devops pipelines 

- Github actions can be used to automate infrastructure by setting a trigger for it to initiate a script 

- Indentation/ formatting is very important when creating pipelines as it needs a clear set of instructions when to do each step 

- Pipeline can be viewed in the actions tab on github 


## Flask 

- Flask depenency in python can be used to host webapps 
- @app.route('/') makes the webapp created the landing/home page on the host
- Networking principle 0.0.0.0 as a host opens it to be accessed by any network/ip


## Docker

- Port mapping as a concept in docker is when you set ports on your machine to ports in your container ; these dont have to be the same eg 8080:5001 
- Requirements.txt file can be used to store dependencies so you can run them as one batch in docker

## Key Commands 

- Docker run -p 5001:5001 docker-flask-app = Runs my app and maps port 5001 on my machine to port 5001 within the container 

- pip3 install flask - installs the dependency flask 

- GithubActions - actions/checkout@v4 - can be used to read your code so that it can execute commands  


# Errors I faced

- Initially tried to use azure services but need to fill out a form to use their devops pipeline

- Pipeline failed : Docker image Build error 

fix: specified a directory in the docker build command which was missing 

- Git merge issue - Local git repo differed from github repo, this is because I tried to use azure and it created files which were not present in my local repo

fix : Pull request from github so they are both the same and merge the data onto the main branch

- Error : Container would not build due to line in code that installs dependencies 'RUN PIP install requirements.txt'

    ### Troubleshooting : 

    - removed this line and tested to see if instead just adding a line to install the dependency flask worked, it did.
        - ran pip in my terminal and it returned an error but pip3 worked, leading me to believe thats where the issue lied.

     -Fix : Changed code to reflect this and everything was functional again 


- Error : port 5000 was in use on my mac for airplay so couldnt be used to host the webpage 

- FIX : changed to port 5001 which wasnt in use therefore worked




