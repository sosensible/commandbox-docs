# Git Endpoint

Entire Git repos that represent a package can be installed via the Git endpoint.  This can be a public Git server like GitHub or Bitbucket, or a private Git repo behind your firewall.  

Make sure the root of your Git repo has a `box.json` inside of it so CommandBox can tell the version and name of the package.  If there is no `box.json`, the name of the repo will be used as the package name.

## Installation

To install a package from a Git repo, use the URL like so:

```bash
install 
```

Note if using Windows, you need to escape backslashes in the command parameter.

```bash
install git://github.com/username/repoName.git
```

## GitHub shortcut

If the repo you wish to install is located on Github.com, you can use this shortcut to specifying the package.


```bash
install username/repoName
```

## In box.json

You can specify packages from folder endpoints as dependencies in your `box.json` in this format.  Remember, JSON requires that backslashes be escaped.

```javascript
{
    "dependencies" : {
        "myPackage" : "git://github.com/username/repoName.git"
    }
}

```

## Authentication

Git repos that require authentication are not currently supported.  You will need to use a repo that allows anonymous pulls.