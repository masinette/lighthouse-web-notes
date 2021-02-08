# Git, Markdown, and the Dev Workflow

## Initializing A New Project

Create a directory in your /vagrant folder called lighthouse-web-notes.
```terminal
cd /vagrant
mkdir lighthouse-web-notes
```
This will serve as the project directory.

Switch into your newly created directory.
```terminal 
cd lighthouse-web-notes
```

Initialize a new git repo in this directory.

```terminal 
git init
```

Create a README file (called README.md) using the Terminal.
```terminal 
touch README.md
```
Add the README.md file to the repository

```terminal
git add README.md
```
Commit your changes

```terminal
git commit -m  "Blank README.md added"
```

## Pushing to Github

We can now push this new repository along with its single commit to a new repository on GitHub.

* Create a new and completely empty repository with the same name on GitHub (website).

* Add the URL of the new repo as a remote on your local repo.
``` terminal
git remote add origin <URL>
```
(Replace <URL> with the URL of your repo)

* Push your changes to GitHub.

```terminal
git push -u origin master
```
