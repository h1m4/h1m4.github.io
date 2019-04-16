---
title: "What is Web Programming"
layout: post
date: 2019-04-16 22:48
image: /assets/images/markdown.jpg
headerImage: false
tag:
- hackathon
- frontend
- bigdata
category: blog
author: Minjeong Kang
description: Markdown summary with different options
# jemoji: '<img class="emoji" title=":ramen:" alt=":ramen:" src="https://assets.github.com/images/icons/emoji/unicode/1f35c.png" height="20" width="20" align="absmiddle">'
---

# What is Web Programming

![Screenshot](https://cdn-images-1.medium.com/max/800/0*0ciaiRWAJ2kFTrYr.jpg)


## How does the Web work?
We all use the internet, most of us, use this every day. But you know how does the web work exactly? It’s more complicated than you type google.com on your browser and press enter. This link will be helpful to know how the Internet works.

[How the Internet works · Django Girls Tutorial](https://tutorial.djangogirls.org/en/how_the_internet_works/)

## What is the Web Programming?
In short, web programming is developing server and client that communicate with HTTP(s) protocol. But we usually develope the server side only. Because we already have nice and neat web clients(web browsers) like Chrome and Safari, but still you can develope the client side if you want.

Let’s make an simple and primary client with Python and request the web page.

```
#example.py
import urllib.request
print(urllib.request.urlopen("<http://www.exapmle.com>").read().decode('utf-8'))
```
You can check the HTML response here. But you do not have to use a web browser to send requests to a web server.

```
<!DOCTYPE html><html data-adblockkey="MFwwDQYJKoZIhvcNAQEBBQADSwAwSAJBANDrp2lz7AOmADaN8tA50LsWcjLFyQFcb/P2Txc58oYOeILb3vBw7J6f4pamkAQVSQuqYsKx3YzdUHCvbVZvFUsCAwEAAQ==_jcd1x7QDTpyAJGmHflZmnAej0PepN/9dkly1Qq+CuZmSPT80nh15QPnreUf0hjd3ZvIRPdmmq+pBvTOWJXRiNQ=="><head><meta http-equiv="Content-Type" content="text/html; charset=utf-8"><title></title><meta name="viewport" content="width=device-width, initial-scale=1"><meta name="description" content="See related links to what you are looking for."/></head><!--[if IE 6 ]><body class="ie6"><![endif]--><!--[if IE 7 ]><body class="ie7"><![endif]--><!--[if IE 8 ]><body class="ie8"><![endif]--><!--[if IE 9 ]><body class="ie9"><![endif]--><!--[if (gt IE 9)|!(IE)]> --><body><!--<![endif]--><script type="text/javascript">g_pb=(function(){var
DY=document,azB=location,DE=DY.createElement('script'),aAD=false,LX;DE.defer=true;DE.async=true;DE.src="//www.google.com/adsense/domains/caf.js";DE.onerror=function(){if(azB.search!=='?z'){azB.href='/?z';}};DE.onload=DE.onreadystatechange=function(){if(!aAD&&LX){if(!window['googleNDT_']){}
LX(google.ads.domains.Caf);}
aAD=true;};DY.body.appendChild(DE);return{azo:function(n$){if(aAD)
n$(google.ads.domains.Caf);else
...
```
This is curl command of Linux if you test this code then you can get the same response as before.
```
$curl <http://www.example.com>
```
Now you know that can send a request as a Web client, even if it is not necessarily a Web browser.

## HTTP Protocol
The HTTP(Hypertext Transfer Protocol) protocol is the communication method used to send and receive data between the web server and the client. It’s work on the TCP/IP protocol. It means web server and web client should have an IP address for TCP/IP protocol.

If you type www.google.com on the web browser and press enter, then client/server connection through HTTP will work. Web client sends the HTTP request message and the web server handle the request and send the result to the client as an HTTP response. This is how the web works.

## HTTP message structure
There are two types in the HTTP messages, one is the request message from the client to the server and the other is response message from the server to the client.

![Screenshot](https://mdn.mozillademos.org/files/13825/HTTPMsg2.png)

The start line called the request line when it’s a request message. When it’s a response message, it called the status message.

This is an example of the request message without a body. The first line is the request line that has the request method, request URL, and the protocol version. Second line is the header. You can skip the Host header if you want.
```
GET <https://www.example.com>::8080/book/shapespeare HTTP/1.1
```
Now let’s see the response message.
```
HTTP/1.1 200 OK
Content-Type: application/xhtml+xml; charset=utf-8
<html>
...
</html>
```
The first status line has the protocol version, status code, and status text. The server displays the processing results in the status line. In this case, the result is `200 ok`. Here we can see that the results have been processed normally.

## HTTP request method
It tells the server how clients are handled via the HTTP method. There are 8 methods in the HTTP method. Of these, the most commonly used are GET, POST, PUT, DELETE. These match up to the CRUD.

## GET method
This is one of the most common methods all of the 8 methods. This requests the data in the URL. Get is used to request data from a specified resource.

Get method sends the data attaching ‘name=value’ after ? in the URL. So, this method has length restrictions. And this remains in the browser history so you should never be used when dealing with sensitive data.

## POST method
POST is used to send data to the server to create/update a resource/ This does not remain in the browser history and have no restrictions on data length.

In Python’s Django web framework, the data in the form is being dealt with only POST method.
