# gitsync - syncs two git remotes

## Usage:

### To sync one repo to another in a one-off job:

    $ gitsync oneshot -s git@gitrepo.com:username/repository.git -t git@otherremote.com:username/new_repository.git

  This will check out everything from the source repo to a temporary directory, 
  push it all to the target repo and delete the temporary directory.


### To set up a long-running job:

    $ gitsync init -s git@gitrepo.com:username/repository.git -t git@otherremote.com:username/new_repository.git [-n reponame]

  This will set up a workspace where a mirror of the source repo will live, 
  and check out that repo. Nothing is synced at this point.

### To synchronise changes in an init'd long-running job

     $ gitsync sync

    This will fetch all upstream changes and push them to the target.

### To remove the workspace for a long-running job:

    $ gitsync clean


