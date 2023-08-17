# Welcome Developers coming from GitHub Enterprise Server to GitHub Enteprise Cloud Managed Users

## Overview of Changes

1. Your username will have an "`_spe`" suffix as can be seen in the upper right corner -- this is just the nature of this version of GitHub Enterprise Cloud.
   <br/>This user is unique to this provisioned instance of GitHub, it cannot be used on the public-facing side of github.com.
   <br/>Similarly if you have an existing github.com username, it cannot be used here.
1. Organizations are now strictly controlled by the DevOps team and will no longer specified by Application Teams.
1. Fine-grained PATs are allowed to be used -- refer to the PATS.MD for further documentation.
1. Personal namespaced repos are no longer allowed (ie. repos under your username).
   If you don't know what that is, then it doesn't apply you.
1. General repository best practices will be enforced:
   * NO binary files to be committed.
   * NO Forks -- use branches.
   * NO SECRETS to be committed.
   * Anything else DevOps might have forgotten.

## Migration of local development environments

Update new GitHub repo location by editing the `<git workspace>/.git/config` file.

1. Find the `<git workspace>/.git/config` file
1. Make a backup copy of it
1. Find the `[remote "origin"]` section in the `.git/config` file
   ```
   [core]
           repositoryformatversion = 0
           filemode = true
           bare = false
           logallrefupdates = true
           ignorecase = true
           precomposeunicode = true
   [remote "origin"]
           url = https://github-scm.spe.sony.com/pli2/test-mule
           fetch = +refs/heads/*:refs/remotes/origin/*
   [branch "master"]
           remote = origin
           merge = refs/heads/master
   ```
1. Change the key `url` value to match the new location of the repo, ex:
   ```
   [remote "origin"]
           url = https://github-scm.spe.sony.com/pli2/test-mule
   ```
   to
   ```
   [remote "origin"]
           url = https://github.com/<new org>/test-mule
   ```
1. `git pull` to verify that it pulls through from the new location

