# Gitodo
###Todo Lists stored on github
================

###What is it?
Gitodo is a simple CLI utility to manage todo list items, using a github repo as the datastore. Todo lists are stored and managed in markdown files.

Gitodo supports sublists inside lists, as well as list/sublist creation, checking off items, listing items, and searching.

###Usage

- [x] Create a new list
`gitodo create FileName`

- [X] Add a new Todo to a list
`gitodo todo FileName "Take Over The World"`

- [x] Checking off a todo item
`gitodo complete FileName "Take Over The World" `

- [x] Creating a sublist:
`gitodo sublist FileName "Sublist Name"`

- [x] Viewing a List
`gitodo show FileName`

- [x] Viewing only uncompleted todos:
`gitodo show FileName --open`

- [x] Viewing only completed todos:
`gitodo show FileName --done`

- [x] Remove a todo:
`gitodo remove FileName "todo"`

- [x] Searching for a todo: 
`gitodo search FileName "todo"`

#### The -f flag
By default Gitodo will throw errors if you attempt to add a todo to a file that does not exist, or to a sublist that does not exist in a file. Adding the -f flag, (or --force) will suppress the errors and create the file or sublist as necessary.

#### The -s flag
If you could like a command to pertain to a sublist only during either `show` or `todo` commands, you may add the -s flag with the list name to follow.

**Example**: `gitodo show FileName -s "Sublist Name" `

If you would like to create a new Todo List with a sublist you can add the -s flag to add the default **General** sublist to the file. You can also add an argument after the -s flag to provide a custom sublist name.

**Example**: `gitodo create FileName -s //adds General sublist`

**With Custom Sublist:**  `gitodo create FileName -s "My Nifty List Name"`

### The -l flag
If you would like to add a link to a todo, you can do that easily with the -l flag. 

**Example**

```
gitodo todo SomeFileName "The Dutch" -l "http://thedutchnyc.com"
```
**Will Result in:**  
`- [ ] [The Dutch](http://thedutchnyc.com)`

### The -h flag
By default gitodo will create a commit for each write action. These are triggered on `create`, `todo`,  `complete`, and `sublist` commands. If you would like to hold a group of changes to be committed at once, you can use the -h flag ( or --hold). The next writeable command will commit all the previously held commands into a single commit.

**Example**

```
gitodo todo TestList "some cool Todo" -h
gitodo todo TestList "another really neat todo" -h
gitodo create NewList -s "Nifty Sublist" // This will commit itself and the two previous todos
```

### The -a flag
When searching for todos, you can add the `-a` or `--all` tag to search every .md file in the current directory. 

**Example**  
`gitodo search "Search Term" --all`

###Installation
Make gitodo executable, and move to a useable place.

```
chmod +x gitodo && cp gitodo /usr/local/bin/
```

Gitodo is not able to be used from inside any git repo you like.

###Upcoming Features

- [ ] Support for Due Dates

- [ ] View due todos
`gitodo show --due`

- [ ] View past due todos
`gitodo show --past-due`
- [ ] Add multiple, todos at once
- [ ] move todo to different list
- [ ] remove sublist
- [ ] complete sublist
- [ ] add ability to have same commit on multiple sublists