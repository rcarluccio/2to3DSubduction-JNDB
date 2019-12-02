[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/rcarluccio/JNDB_RC_-Subd/master)



# JNDB_RC
JNDB combined the use of jupyter notebooks, docker containers and binder to improve education and reproducible research.

Busting the docker Myth!   

Would you like to easily share your data and research findings with your research team and the community to receive prompt feedback and improve reproducibility?

The  integrated use of Jupyter Notebooks, docker containers and binder (JNDB) can allow you to do this in a timely manner! No need to spend days and days re-boosting your system and dependencies anymore! Just follow these few steps and you’ll be able to get the ball up and running in a blink of an eye! 

The key benefit of Docker is that it allows users to package an application with all of its dependencies into a standardized unit for software development. Unlike virtual machines, containers do not have high overhead and hence enable more efficient usage of the underlying system and resources.

You can think of a Docker’s image like a picture of a specific landscape and a container like everything that is part of the picture and makes it unique. Containers include everything underneath that makes images run and can make them run again, as that you can recreate the same picture whenever doesn't mather what machine you're using.

1.	Get docker up running on your machine:

    •	Install on Mac or windows https://docs.docker.com/docker-for-mac/install/ or https://docs.docker.com/docker-for-mac/install/
    •	Intro to docket: https://docker-curriculum.com and Orientation and setup https://docs.docker.com/get-started/
    •	Basic docker commands: https://github.com/underworldcode/underworld2/blob/master/docs/cheatsheet/cheatsheet.pdf and https://underworld2.readthedocs.io/en/latest/Installation.html

2.	Select your favourite version of uw2 images from the docker hub:
    •	https://hub.docker.com/r/underworldcode/underworld2/tags?page=1&name=2.5. 
    •	 Launch docker on your terminal (e.g. type 
        $docker images
        $docker pull underworldcode/underworld2: 2.6.0b
        $docker run -p 8888:8888 -v $PWD:/workspace underworldcode/underworld2:2.6.0b 
    •	Test that your ipyb script is compatible with the image you’ve selected. To do this: open your uw2 script through the image by copying and pasting the url you were given (e.g  http://localhost:8888/tree/2D_PP/2D_PPsimplified)

3.	Upload the repository you want to share (after you’ve tested it in local) on github.
    •	 N.B avoid saving heavy data on github, use inline plotting tools instead (e.g LavaVu, MatplotLib or Plotly)
    •	Basic shell commands you need to know include:
        $git clone https://github.com/<username>/repo-name.git
        $ git remote add origin https://github.com/<username>/repo-name.git
        $ git add --all
        $ git commit -m 'initial commit'
        $ git push -u origin master
        $git status
        $git commit -m 'fixed Dockerfile'
        $git push
    •	Write a README.txt file to explain the nature of your script
    •	Write a Docker file, this will allow you to connect your github repository, with the uw2 image and the binder instance.
    •	For example:
    
    
        # UW image used:
        FROM underworldcode/uw2cylindrical:cylindrical

        # Git run my repo:
        RUN git clone https://github.com/rsbyrne/demonstration.git

    •	NB. it does not need the txt extension

4.	Binder is great for creating a live, interactive environment for your code.

    •	Go to mybinder.org
    •	Follow the instructions to create your binder instance. Note that your new binder instance will be kept forever: it will always have the same URL, which you can email to people or put on Facebook or whatever.
    •	If you update your git repository you’ll need to generate a new binder URL.

5.	Notebook Viewer is a part of the Jupyter ecosystem whose job is to make notebooks look nice.
    •	Get the URL of the thing you want to see: for example, the URL of your git repository, or the URL of a specific notebook file inside your repository.
    •	Take the https:// and other stuff off the front of your URL and replace it with nbviewer.jupyter.org
    •	For example:
        
        https://nbviewer.jupyter.org/github/rsbyrne/demonstration/blob/master/MS98_demo/MS98.ipynb

        with nbviewer:
        https://nbviewer.jupyter.org/github/rcarluccio/JNDB_RC_2D/blob/master/2D_PP/2D_PPsimplified/2D_PP.ipynb#

6.	QR generator:
    •	For example, https://www.qr-code-generator.com


7. to show a binder badge you need to compy your binder instance in your read me gile, as:



