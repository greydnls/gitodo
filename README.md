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

- [  ]Creating a sublist:  
`gitodo sublist FileName "Sublist Name"`

- [  ] Viewing a List  
`gitodo show FileName`

- [  ] Viewing only undone todos:   
`gitodo show FileName --open`

- [  ] Viewing only undone todos:   
`gitodo show FileName --done`

#### The -f flag
By default Gitodo will throw errors if you attempt to add a todo to a file that does not exist, or to a sublist that does not exist in a file. Adding the -f flag, (or --force) will suppress the errors and create the file or sublist as necessary. 

#### The -s flag
If you could like a command to pertain to a sublist only during either `show` or `todo` commands, you may add the -s flag with the list name to follow.   

**Example**: `gitodo show FileName -s "Sublist Name" `

If you would like to create a new Todo List with a sublist you can add the -s flag to add a the default **General** sublist to the file. You can also add an argument after the -s flag to provide a custom sublist name. 

**Example**: `gitodo create FileName -s //adds General sublist`

**With Custom Sublist:**  `gitodo create FileName -s "My Nifty List Name"` 

#### The -a flag 
If you would like to show all todos, from all lists you can use the -a or --all flag.   
**Show all todos:** `gitodo show --all`
