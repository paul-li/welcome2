# Welcome Developers coming from GitHub Enterprise Server to GitHub Enteprise Cloud Managed Users

## Overview of Changes

1. Your username will have an "`_spe`" suffix as can be seen after clicking on your avatar in the upper right corner -- this is just the nature of this version of GitHub Enterprise Cloud.
   * <strong>This user is unique to this provisioned instance of GitHub, it cannot be used on the public-facing side of github.com.</strong>
   * <strong>Similarly if you have an existing github.com username, it cannot be used here.</strong>
1. Organizations are now strictly controlled by the DevOps team and will no longer be specified by Application Teams.
1. Fine-grained PATs are permitted for use -- refer to the PATS.MD for further documentation.
1. Personal namespaced repos are no longer allowed (ie. repos under your username).
   If you don't know what that is, then it doesn't apply you and you have nothing to worry about.
1. General repository best practices will be enforced:
   * <strong>NO binary files to be committed.</strong>
   * <strong>NO Forks -- use branches.</strong>
   * <strong>NO SECRETS to be committed.</strong>
   * <em>Anything else DevOps might have forgotten.</em>

## Migration of local development environments

Update new GitHub repo location by editing the `<git workspace>/.git/config` file.
If you do not know what `<git workspace>` is, it is the directory that you `git clone`d into (ie. your application/project directory).

1. Find the `<git workspace>/.git/config` file
1. Make a backup copy of it
1. Find the `[remote "origin"]` section in the `.git/config` file
   An example of the contents of this file as shown:
   ```ini
   [core]
           repositoryformatversion = 0
           filemode = true
           bare = false
           logallrefupdates = true
           ignorecase = true
           precomposeunicode = true
   [remote "origin"]
           url = https://github-scm.spe.sony.com/mp/test-mule
           fetch = +refs/heads/*:refs/remotes/origin/*
   [branch "master"]
           remote = origin
           merge = refs/heads/master
   ```
1. Change the key `url` value to match the new location of the repo, ex:
   ```ini
   [remote "origin"]
           url = https://github-scm.spe.sony.com/mp/test-mule
   ```
   to
   ```ini
   [remote "origin"]
           url = https://github.com/<new org>/test-mule
   ```
   If you do not know the value of `<new org>`, please contact your technical lead/architect or SPE representive if you are a non-SPE developer.
1. `git pull` to verify that it pulls from the new location.

