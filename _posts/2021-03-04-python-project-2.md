---
layout: post
title:  "Writing a Python API Wrapper"
date:   2021-03-05 20:00:00 -0000
categories: posts
tags: posts, python, project, intermediate, api
img: "api-code.png"
---

# Writing an API Wrapper for a REST-API in Python

First, play around with the API. use the python *requests* module for this, it is easy to understand and make some HTTP GET calls to the API. This way, you can learn to interact with the API. For example, make a simple request for the status code to a URL like GitHub

```python
import requests 
#import the request package

response = requests.get('https://github.com') 
#make a HTTP GET request to github.com and save the response in a object
print(response.status_code) #print the response
```

This outputs:

```
200 
```

Which is basically the HTTP Code for OK. Now lets write the API class.

### the central API Class

First, start with the central API Class. This Class will be initialized at the beginning by the User and then used for every call to the web-API. If you don't know enough about classes in Python, take a look at [this great video](https://www.youtube.com/watch?v=ZDa-Z5JzLYM). Without some Knowledge of it, you will not be able to understand everything

```python
class API():
  """ the API Class"""
  def __init(self):
    """ Initialize a API Class"""
    self.url = "https://yourapi.example.com" 
```

I would recommend setting the URL once and then using it everywhere, This way you can easily change it if the API Endpoint changes and push your updates. Otherwise, you will have to manually change the url everywhere you used it

### Authentication

Most APIs use some kind of Authentication, often with OAuth or a X-Header. (Twitter, NYT etc...), to protect themselves from DDos Attacks and set limits on every user. So you will have to provide a method in the API Class to authenticate with the API

```python
	#still part of the class API
  def set_token(self, token):
    """ Authenticate with the API"""
    self.token = token
    #simply set the token
```

You could also test the validity of this token, but this is something for later. For now, you just set the token.

### GET Method

This part depends heavily, on what you want to do with your API and how your API is structured, but there is some help I can give you. In this example, I assume you authenticate with the API via a X-Authorization Header

```python
	def get(self):
    """ the get method of your Class"""
    response = requests.get(url = self.url, headers = {"X-Authorization": self.token}, params = {"Whatever 	Params you need": "Lorem Ipsum"}
                           )
    return response
```

This method uses the requests GET method with the URL you set as an argument and your token from the authorisation as the Authentication. 

## Your Class in Use

Now, how would a user use this? Lets see an Example

```python
#set the API Class and linkt it to the api object
api = API()

#now set the token
api.set_token("your token") #here, the user would input their token

#now get something from the API
api.get()
```

Et voila, you have written a simple API Wrapper. Of course you can expand this via adding many more methods to the API Class and building different Classes that parse the responses from the Get Methods, but this all depends on your API and is therefore difficult to show

If you want to take a look at an Example, visit my Github Repo, where I have written an API Wrapper for a german newspaper API

[GitHub](https://skriptum.github.io/zeit) 

Dont hesitate to drop me an email at [kkx@protonmail.com](mailto:kkx@protonmail.com) if you have more questions

