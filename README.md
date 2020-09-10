# Nethive CVSS Control Panel Utilities

A tool that allows you to interact with the summarizer.

summarizer source-code can be found here : https://github.com/Falanteris/docker-nethive-cvss/

summarizer can be installed in two ways.


1. Directly Pulling and Running the image.

Currently, we have created a docker registry that stores the image. It's hosted in http://rk-sragen.site:5043/nethive-cvss. You can login as a pull-only user with the following credentials.

    $ docker login -u cvss -p pullmyimage nethive.me/cvss
    $ docker pull nethive.me/cvss
    $ docker tag nethive-cvss nethive.me/cvss

this would pull the image directly into your docker system and install it, depending on your connection speed, it may take a while. The image is also being re-build everyday with Jenkins CI. So that newer users can quickly catch up to speed to the latest changes in NVD data as the image builds includes NVD data integration as well.

After pulling, you can navigate yourself to the location of this control panel folder and execute the *cvss* bash script. If you open the script, it contains environment variables that you can modify to fit your system's architecture (e.g. remote kafka or ES server, different secret, different ES index, etc.). Once you're done, execute the script and the system should run like a charm.

You can interact with the summarizer's docker container using the scripts we've included in the *docker-utils* folder. There you will find things that allows you to trigger updates, check for services, and even accessing the container's bash itself.

2. Building from Scratch.

If you don't like typing docker login passwords and/or prefer to build it your own, then we've got you covered!. Clone the repository, build it under the tag-name *nethive-cvss* like so.

        $ git clone https://github.com/Falanteris/docker-nethive-cvss
        $ cd docker-nethive-cvss
        $ docker build -t nethive-cvss .
        $ ./cvss

And we're done!. The nethive-cvss system would run smoothly. Of course you can edit the *cvss* script to fit your system architecture. But other than that, it should accomplish the same thing that the first method did. Only with more processing power required since you would need to build the image yourself. 

Now about the utilities...

There are some, but we're planning to add more in the future (perhaps). Some of which have been mentioned before



