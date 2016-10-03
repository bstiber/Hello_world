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
