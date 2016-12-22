# Deploying OpenStack using containerized infrared
------------------------------
## Setting up jenkins

* Install docker plugin
* Setup new cloud in Jenkins setting page
	![docker slave setting] (img/docker-plugin-global-config.png)
* Assign lable to the newly created slave
* Configure the job to run on docker slave

## Create docker image for jenkins slave

* Clone [repo](https://github.com/ovorobio/infrared-docker.git) with ansible tasks for build docker conatiner
* Inside the repo run `ansible-container build`
* After the image is created uplopad it to the registry with `docker push` command
* Download the image to the host where docker slave will be executed with `docker pull` command
