#Git, Working solo setup
When working alone on a project, we do not need to use a .pairs file. We do this with a global configuration in the terminal:

```ruby
$ git config --global user.name "Padma Patil"
$ git config --global user.email padma@email.com
```

```ruby
# To confirm that we are where we think we are, we can always show our location with a pwd:
pwd
=> /Users/billstiber-admin/documents/hello-world
```

##Initializing Git and Git pair
The next step before we create a single file for our hello-world website is to create a Git directory within our project directory that will track everything we add, modify and delete.
We do this by initializing a new Git repository:
```ruby
$ git init
=> Initialized empty Git repository in /Users/billstiber-admin/Documents/hello-world/.git/
```

Now if we do an ls, we might expect to see the new directory. But where is it? Directories beginning with a . are called hidden files and do not appear when you list the files with an ls. To see hidden files, we have to add a modifier to our ls command, -a which tells our terminal to list all:
```ruby
ls -a
=> .git
```
#Pushing to GitHub
With an empty repository awaiting our code, we can now follow the steps to push our code from our local repository to the remote repository.

In our project directory, we will make sure our code is working. In this case, we open it in the browser and it looks good. We also ensure that there aren't any outstanding changes that we still need to commit:
```ruby
$ git status
```
Now we need to tell Git where our remote repository is by providing the web address. We'll use the git remote command.

```ruby
$ git remote add bs https://github.com/bstiber/Hello_world
```

This command tells Git to store information about a remote repository that we gave the nickname, al (the initials for one partner - Ada Lovelace) located at https://github.com/bstiber/Hello_world. We could use any nickname for the remote but we've chosen bs for Bill Stiber.

To see that Git has done this successfully, we can run this command:
```ruby
$ git remote -v
bs	https://github.com/bstiber/Hello_world (fetch)
bs	https://github.com/bstiber/Hello_world (push)
```

This shows us all the remotes stored in Git for this project. In this case, we only have one, with the nickname bs.

To push our code, which means we are copying it from the local to the remote, we run this command:
```ruby
$ git push bs master
```

#Cloning from GitHub
So, how do we get our code back to our local from the remote? What if we push our code up to GitHub at Epicodus and want to work on it at home on our personal devices? To do this, we'll need to clone our GitHub repository on our local machines.
To practice this, let's delete our hello-world project directory and clone it again from GitHub. To delete a whole directory, we can't be in it so we'll go up a directory level and then remove it:

```ruby
$ cd ..
$ rm -rf hello-world
```
Poof! Gone. Now, if we want to copy it in the exact same location from GitHub, we get the URL for the remote repository and run:

```ruby
$ git clone https://github.com/bstiber/Hello_world
```
Now, an ls shows us our directory is there with our code file in it. Let's go into the project directory:

```ruby
$ cd hello-world
```

If we do a git log, we see that our commit history arrived with our directory and code.

If we run git remote -v, we also see that our newly created local .git repository is automatically linked - with the nickname origin - to the remote repository from which we cloned.

```ruby
$ git remote -v
origin	https://github.com/bstiber/Hello_world (fetch)
origin	https://github.com/bstiber/Hello_world (push)
```
If we make changes to the code and want to push again, we would be able to use the origin nickname that came with the repository from GitHub (e.g. git push origin master).

Note: only one location can be designated with the nickname "origin". So, if we clone one project but want to push to two different repositories, they cannot both be nicknamed "origin". That is another good reason to use your initials as the nickname of the remote repository.

Whew! This has been a mountain of Git concepts and terminology to explore. Don't try and memorize this information. Use the cheat sheets for reference to walk through set up and usage in your projects to come. Before you know it, it'll become ingrained in your daily workflow.
Be sure that you are not cloning a project inside of an existing local repository. In other words, you should not be inside of a project directory when you run the git clone command. Otherwise you'll end up with one git repository inside of another.
