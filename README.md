# Gitodo
###Todo Lists stored on github
================

###What is it?
Gitodo is a simple CLI utility to manage todo list items, using a github repo as the datastore. Todo lists are stored and managed in markdown files. 

Gitodo supports sublists inside lists, as well as list/sublist creation, checking off items, listing items, and searching. 

###Usage

Create a new list    
`gitodo create FileName`

Add a new Todo to a list    
`gitodo add FileName "Take Over The World"`

For convenience, you can also create a new list in the process of adding the todo:  
`gitodo add FileName "Take Over The World" -f`

Checking off a todo item
`gitodo complete FileName "Take Over The World" `

Creating a sublist:  
`gitodo add FileName "TakeOver The World" ` -l="Sublist Name"`

Viewing a List  
`gitodo show FileName`

Viewing a single sublist only  
`gitodo show FileName -l="Sublist Name"`

Viewing only undone todos:   
`gitodo todo FileName`

Viewing undone todos from a sublist:   
`gitodo todo FileName -l="Sublist Name"`

