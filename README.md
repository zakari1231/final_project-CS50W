# Final-Project !
Web Programming with Python and JavaScript

# Introduction

This a simple chat application using Django channels and javascripts and the redis server

## Overview

This chat app is a Django javascripts app that focused on giving a "virtual room" or space to interact and have fun, especially this day where you can not have a fully private conversation on basically any chat app.
You can use this app to chat with your friend on a channel only you and your friend know this app provides interactions in real-time.

Inside each room, firends cans send messages to each other in real time and every thing will be saved in a database in case one of your friends did come in time he will be able to see what you message you send to him 


### Short Demos of Main Features

## Main Page


When you first enter the web site you will see the main page that contains 2 inputs the first one is for the room number that you cans share with your friend (this way you and your friend are the only one who can read and write messages to each other), when you enter your name and the number room you can go directly to the chat room. 

![main page](/screenshot/1.png) 

## Chat Room

The chat room contain the messages container, and the message input field and the send button when you writ a message in the message input field and click on the send button or you click the enter button on the keyboard the message will appear on the message container and the message will be send to every one ho is connected the test room and saved in the database

![Chat Room](/screenshot/2.png)

the web site is responsive you can use it with all types of devices, we use a simple CSS and a bootstrap to make it happened, and to make the user experience simple and easy to understand 

![Chat Room](/screenshot/3.png)



### Architecture

**Frontend**
- Languages: 
 	* JavaScript
	* HTML
	* CSS
- Main Framework/Libraries:
	* [Bootstrap](https://getbootstrap.com/)
	

**Backend**
- Language: 
	* Python
- Main Framework/Libraries:
 	* [Django](https://www.djangoproject.com/)
	* [Django Channels](https://channels.readthedocs.io/en/latest/)

**Database**
- PostgreSQL

**files**
- 1/ consumers.py 
In this file the back-end of Django channels we create a class that take care of the connect, disconnect device message and send message all functions are running asynchronous using the keyword since and when ever the function should run in synchronous we use the keyword await
In short, this class connects every user to a channel, and when one of the users sends a message this class send it to all the users connected to this channel 
- 2/ models.py 
We are using the red is server that means every message is in temporary memory of a channels, but if we refresh the page all message will be gone that why to save this message in the database to save them, even if we refresh the message will still there Containe the back-end of view of every html file in our case 2 page the home page and the chat room
- 4/ url.py 
Responsible for every path of this application 

- 5/ asgi.py 
ASGI is structured as a single, asynchronous callable. It takes a scope, which is a dict containing details about the specific connection, send, an asynchronous callable, that lets the application send event messages to the client, and receive, an asynchronous callable which lets the application receive event messages from the client.

- 6/ index.html
This html file is the main page that contains the input fields of the room number and the name of the user this page is style using the bootstrap and a simple css
- 7/ room.html 
This html page is the chat room it contain the javascript code that allow to show every new receiving message and automatically update the messages container without reloading the page, And also scroll the page to the bottom when there is e new message to appear in the page And also a function that allow the enter key in the keyboard the work as a send button




###  How to run your application

Tho run this application follow the following stpes 

- `1`

```
git clone https://github.com/zakari1231/cs50web-final-project.git
```
or download this project from the download button 

-`2` - create a new virtual environment using 

```
Virtualenv –p py final_project
```

-`3` - Active virtual env using 

```
final_project\Scripts\activate
```

-`4` - install requiremment 

```
pip install -r requirements.txt
```

-`5` - Run those following commands to migrate database.

```
py manage.py makemigrations
py manage.py migrate
```

-`6` - install redis server

If you are on windows download it from this [link] (https://github.com/microsoftarchive/redis/releases/tag/win-3.2.100)

and after installing it, on a separated CMD or your terminal write the following 

```
redis-server --port 6380 --slaveof 127.0.0.1 6379
```
if you are on mac or linux just run this 

```
redis-server
```

When all of this done , you can run this command to run your server.

```
py manage.py runserver 
```

-`7` - enter the room number and your name and that all 



# Finally

Thanks for all people make CS50's Web Programming with Python and JavaScript possible. Especially, thanks for Brain Yu's excellent lecture and his "great question", which motivate me to finish this changing life course.





