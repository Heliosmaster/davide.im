# Davide.im

The n+1-th iteration of my blog. Powered by Jekyll, based on Incorporated.

## Deployment

A bare git repo is in the server, with the following post-receive hook:

    #! /bin/sh
    GIT_REPO=$HOME/davide.im.git
    TMP_GIT_CLONE=$HOME/tmp/davide.im
    PUBLIC_WWW=/var/www/davide.im

    git clone $GIT_REPO $TMP_GIT_CLONE
    cd $TMP_GIT_CLONE
    jekyll build -s $TMP_GIT_CLONE -d $PUBLIC_WWW
    cd
    rm -Rf $TMP_GIT_CLONE
    exit
