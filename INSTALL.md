

# ANNS Installation Instructions
Here we will set up our work environment to launch Jupyter notebooks from a Docker container.  

## Table of Contents:
* [Linux (Ubuntu 14.04 and 16.04)](#ubuntu)
* [Mac](#mac)
* [Windows](#windows)
<a name="ubuntu"></a>
## Linux (Ubuntu 14.04 and 16.04)
Open a bash terminal and execute the following:
### Step 1 – Install Git
```sh
sudo apt-get install -y git
```
### Step 2 - Install Docker
You can follow the instructions found [here](https://docs.docker.com/engine/installation/linux/docker-ce/ubuntu/#install-docker-ce-1), otherwise see below:
#### Ubuntu 14.04 (Trusty)
add below script in addition to the 16.04 script:
```sh
sudo apt-get update
sudo apt-get install \
linux-image-extra-$(uname -r) \
linux-image-extra-virtual
```
#### Ubuntu 16.04 (Xenial)
```sh
sudo apt-get install -y curl
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
sudo apt-get update
sudo apt-get install -y docker-ce
sudo service docker restart
```

### Step 3 - Clone the anns git repo
```sh
git clone https://github.com/mikaellaine/anns.git
```
### Step 4 - Launch the docker image (This can take some time)
```sh
docker-compose up
```
### Step 5 - Launch a Jupyter Notebook within the `anns` Docker container
```sh
docker-compose up
```
If successful, the jupyter notebook will be served to a URL as shown below. Copy and paste the url to your browser.
```sh
[I 21:19:15.056 NotebookApp] Writing notebook server cookie secret to /root/.local/share/jupyter/runtime/notebook_cookie_secret
[I 21:19:15.341 NotebookApp] Serving notebooks from local directory: /
[I 21:19:15.341 NotebookApp] 0 active kernels
[I 21:19:15.341 NotebookApp] The Jupyter Notebook is running at:
[I 21:19:15.341 NotebookApp] http://0.0.0.0:8888/?token=c07276cd245086f751443f74e594f788298ddd24c87dfef4
[I 21:19:15.341 NotebookApp] Use Control-C to stop this server and shut down all kernels (twice to skip confirmation).
[C 21:19:15.342 NotebookApp] 
    
    Copy/paste this URL into your browser when you connect for the first time,
    to login with a token:
        http://0.0.0.0:8888/?token=c07276cd245086f751443f74e594f788298ddd24c87dfef4
```
### You're all Done!  

<a name="mac"></a>
## Mac
The following are installation instructions for Mac on the command line:
### Step 1 – Install Git
Follow the instructions found [here](https://www.atlassian.com/git/tutorials/install-git#mac-os-x)
### Step 2 - Install Docker
Follow the instructions found [here](https://docs.docker.com/docker-for-mac/install/)

### Step 3 - Clone the git repo
```sh
git clone https://github.com/mikaellaine/anns.git
```
### Step 4 - Pull the Docker image
```sh
docker-compose anns
```
If successful, the jupyter notebook will be served to a URL as shown below. Copy and paste the url to your browser.
```sh
[I 21:19:15.056 NotebookApp] Writing notebook server cookie secret to /root/.local/share/jupyter/runtime/notebook_cookie_secret
[I 21:19:15.341 NotebookApp] Serving notebooks from local directory: /
[I 21:19:15.341 NotebookApp] 0 active kernels
[I 21:19:15.341 NotebookApp] The Jupyter Notebook is running at:
[I 21:19:15.341 NotebookApp] http://0.0.0.0:8888/?token=c07276cd245086f751443f74e594f788298ddd24c87dfef4
[I 21:19:15.341 NotebookApp] Use Control-C to stop this server and shut down all kernels (twice to skip confirmation).
[C 21:19:15.342 NotebookApp] 
    
    Copy/paste this URL into your browser when you connect for the first time,
    to login with a token:
        http://0.0.0.0:8888/?token=c07276cd245086f751443f74e594f788298ddd24c87dfef4
```
### You're all Done!
<a name="windows"></a>
## Windows
### Step 1 – Install Git
Follow the instructions found [here](https://www.atlassian.com/git/tutorials/install-git#windows)  
All default options in the installer should work fine.
### Step 2 - Install Docker
Follow the instructions found [here](https://docs.docker.com/toolbox/toolbox_install_windows/)

### Step 3 - Clone the git repo
Open Git Bash, copy and and right-click-->Paste the following command:
```sh
cd ~
git clone https://github.com/mikaellaine/anns.git

```
The repository should now be located at `C:/Users/YourUserName/anns`.
### Step 4 - Copy the Docker IP Address (Windows Only)  
Open the Docker Quickstart Terminal. It will automatically install VirtualBox VM and launch the Docker CLI tool.  
Once the CLI Tool is initialized, you will see a Whale image along with an IP address. This IP address is important since we will need it to access our Jupyter notebook.  
```sh


                        ##         .
                  ## ## ##        ==
               ## ## ## ## ##    ===
           /"""""""""""""""""\___/ ===
      ~~~ {~~ ~~~~ ~~~ ~~~~ ~~~ ~ /  ===- ~~~
           \______ o           __/
             \    \         __/
              \____\_______/

docker is configured to use the default machine with IP 192.168.99.100
For help getting started, check out the docs at https://docs.docker.com

Start interactive shell

khoun@DESKTOP-3S60RT0 MINGW64 ~
$
```
In the above example the IP address is **192.168.99.100**. Please write this down or copy it to a text file for use in Step 7.
### Step 5 - Pull the Docker image
Open the Docker Quickstart Terminal. It will automatically install VirtualBox VM and launch the Docker CLI tool.  

Run these commmands:
```sh
cd
cd anns
docker-compose up

```

If successful, the jupyter notebook will be served to a URL as shown below.  
In Windows we cannot simply copy the URL since it is running in a VirtualBox on top of Windows.  
*Instead* we will need to copy the generated token at the end of the URL.  
```sh
[I 21:19:15.056 NotebookApp] Writing notebook server cookie secret to /root/.local/share/jupyter/runtime/notebook_cookie_secret
[I 21:19:15.341 NotebookApp] Serving notebooks from local directory: /
[I 21:19:15.341 NotebookApp] 0 active kernels
[I 21:19:15.341 NotebookApp] The Jupyter Notebook is running at:
[I 21:19:15.341 NotebookApp] http://0.0.0.0:8888/?token=c07276cd245086f751443f74e594f788298ddd24c87dfef4
[I 21:19:15.341 NotebookApp] Use Control-C to stop this server and shut down all kernels (twice to skip confirmation).
[C 21:19:15.342 NotebookApp] 
    
    Copy/paste this URL into your browser when you connect for the first time,
    to login with a token:
        http://0.0.0.0:8888/?token=c07276cd245086f751443f74e594f788298ddd24c87dfef4
```
Copy the generated token to a text file (in the above example the token is **c07276cd245086f751443f74e594f788298ddd24c87dfef4**)

### Step 7 - Open a Browser and Navigate to our Docker IP Address at port 8888 (Windows Only)
Recall from step 4 we copied the IP address of the Docker container (eg. 192.168.99.100).  
Open a brower and navigate to **192.168.99.100:8888**. You will be prompted to enter a token. Enter the token copied from Step 6 and click **Log In**. You should now be able to access the Jupyter notebooks.  

### You're all Done!
