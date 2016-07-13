If you have a project.git.bundle file and you want to restore it to a service do the following

Set up a new repository on your server
```
git clone project.git.bundle path_to_repo
cd path_to_repo
git remote rename origin bundle
git remote add origin git@bitbucket.org:account/project.git
git push -u origin --all
git push origin --tags
```

Get the list of all branches
`git branch -r`

For every branch listed
```
git checkout <branch>
git push -u origin
```
