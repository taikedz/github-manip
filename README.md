github-do
===

Basic command line operations to control github repositories. You do not need to have any repositories cloned locally.

Written during a cleanup session...

You would make your life easier by using a Personal Access Token - go to `Github.com > (Profile menu) > Settings > Developer Settings > Personal Access Tokens`

Generate a token that has full `repo` and `delete_repo` access; store the PAT somewhere safe as you won't be able todisplay it again. Make sure after copying that there aren't extraneous space characters in your clipboard copy.

## Batch operations

Create repositories:

    github-do create OWNER REPOS ...

Transfer repositories to another user/organisation:

    github-do reown OWNER NEWOWNER REPOS ...

Delete repositories:

    github-do delete OWNER REPOS ...

Rename by substitution:

    github-do srename OWNER SUBSTITUTION REPOS ...

    # e.g. github-do srename myuser "s/^/old-/" project1 project2 project3
    # Renames github.com/myuser/project1 to github.com/myuser/old-project1 ,
    #   and same for other projects listed

## Single-repo operations

Simply rename a project

    github-do rename OWNER REPO NEWREPO

Delete a branch from a repo

    github-do branch delete OWNER REPO BRANCHNAME

Delete a tag on a repo remotely

    github-do tag delete OWNER REPO TAGNAME

## Extending and "Compiling" `github-do`

`github-do` uses [bash-builder](https://github.com/taikedz/bash-builder/) and its associated [libs](https://github.com/taikedz/bash-libs/) to intelligently concatenate the shell sources.

You can write additional functions using [The Github API](https://developer.github.com/v3/) (v3 linked)
