Notes on with Aaron feb 28th First meeting.


def: Credential - OLAF, it allows authorization for google drive. Like a bouncer giving you a wirstbrand to go in.

def: Singularity is like Docker. But its for savio and high performance computing systems. eventually we will use it. 

1) We are looking backward through the notebook. To get a high level overview of whats happenings. ( the notebook Adam shared in the general slack channel

2) We just downloaded the docker and made an account 
Its doing its thing in my top toolbar 

3) we are running commands in docker. 
  a) open terminal
  b) docker run -it ubuntu
  c) docker run -it ubuntu
now we are in a docker container.
type "exit" to exit out of it. 

to open docker container run:
```
docker run -it ubuntu
```

to exit: `exit`

6) created a new git repo for myself. 
7) added Aaron as a colloborator 

8) added this file note. 
9) told Adam that we need our team to be submitted to Savio people. 

Alan:
  So the savio cluster is something we are using, but that isn't the main focus per say. Its about connecting it to everything like google drive and working it seamlessly through all the clould services we are using the shared notebook 

![Savio JupyterHub HTC](https://github.com/alanscha/ancient-world-sp19/blob/master/savio-jupyterhub-htc.png "Savio JupyterHub HTC")

March 21st 2019, Alan and Aaron

for today's session we'll use three things:
1) your own laptop with Docker installed
2) the Data Science Education Program (DSEP) JupyterHub infrastructure: https://datahub.berkeley.edu/
3) Savio JupyterHub: https://jupyter.brc.berkeley.edu/

Note: The following was done on Mac OS.
An Image is like a vitual machine , and a Container is what is running that version. 

We are using iterm2 because of Aaron's reccomendation.

To get the datascience notebooks docker container, run: This will take around 6gigs.
```
docker rm -f aw; docker run -d -p 8888:8888 -v $(pwd):/home/jovyan --name aw jupyter/datascience-notebook jupyter notebook --ip=0.0.0.0 --NotebookApp.custom_display_url=http://127.0.0.1:8888; sleep 2; docker exec aw jupyter notebook list
```

Install homebrew, a package manager if you haven't yet. For macOS only:
```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

Using the cask keyword, install Iterm2
```
brew cask install iterm2
```

Now using the iterm2 terminal, we will create a directory that we will work in so standardize this procedure:
Make sure you are in your root directory. Follow its instructions to give it permissions.

```
mkdir -p ~/work/
cd ~/work
```

Now we will clone relevant repositories.
```
git clone https://github.com/alanscha/ancient-world-sp19/
git clone https://github.com/ucberkeley/brc-cyberinfrastructure/
```

enter the brc-cyberinfrasturcture with 
```
cd brc-cyberinfrastructure
```

Finally, to get the right version:
```
git checkout dev
```

re-run docker command:
```
docker rm -f aw; docker run -d -p 8888:8888 -v $(pwd):/home/jovyan --name ancient-world jupyter/datascience-notebook jupyter notebook --ip=0.0.0.0 --NotebookApp.custom_display_url=http://127.0.0.1:8888; sleep 2; docker exec ancient-world jupyter notebook list
```

click the link provided by this command to open the jupyter notebook file interface.
Now we have access to the notebooks!






