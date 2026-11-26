+++
title = 'Computer Science Principles Unit 2 Review F'
date = 2026-11-26T15:24:51-06:00
author = "Roy Alvarez"
draft = false
+++

## Overview
In this section, we will explore the term world wide web, and how web browsers are able to access it.
We will also learn about the domain name system and how it makes searching the world wide web easier. We will see how it is used, and the internals of how the system functions.
Finally, we will explore how web browsers fetch content from a URL.

### Defining the World Wide Web
Before addressing the world wide web (www), we need to understand that the internet and www are not the same thing.

The internet is the infrastructure, all the computing devices and their connections, and the protocols that dictate how communication should happen.

Whereas the www is a service on the internet - a section on the internet.

Now that we have made the distinction, lets define the world wide web.

The world wide web is a global collection of webpages, programs, and files all accessed by URIs, specifically an URL.

#### Accessing the world wide web
To access the www, we use web browsers.

A web browser is an application that accesses the world wide web and all of its content. It too, uses protocols.

Lets see what protocols are used when loading a webpage like this article.
1. The web browser uses a domain name system to convert the human readable URL into the associated IP address.
2. It then uses the hypertext transfer protocol to request the content residing at the IP address.

Optionally, the web browser might use the transport layer security protocol in order to serve the content with a connection that is secure and encrypted.

That being said, the web browser uses these protocols on top of the internet protocols. This means that when using the hypertext transfer protocol, we are also using the TCP/IP stack.

### Defining Domain Name System
The domain name system (DNS for short) is a mapping of human readable names, called domain names, to IP addresses.

This makes it so that you need not type IPv4 and IPv6 addresses in your search engine, and instead, for example, type the simple google.com address to arrive at google.

#### Sections of the Domain Name
A domain name, like docs.google.com, is made up of sections. And it is processed from right to left.

Lets examine the domain name skeleton from right to left:
1. Top level domain (TLD for short).
2. Second level domain.
3. Third level domain (sub-domain).

The top level domain uses a limited set of names, but most websites use the common TLDs such as .com, .edu, and .org.

The second level domain is a unique name registered by an individual or organization, like google or microsoft.

The sub-domain belongs to the same group  who registered the website, and it links to a subsection of the website, like docs or spreadsheets.

#### DNS Conversion Process
The domain name system must convert the human readable URL into its IP address so that we can send and recieve data to that device hosting the resource.

This conversion is a fallthrough process since not every single website on the web can be cached by our device in a local database.
1. Check local Cache.
2. Ask ISP Cache.
3. Ask name servers.

##### Check Local Cache
The browser will cache mappings of domain names to IP addresses locally. Overtime, the websites that are not getting used anymore, the browser will clear that space so that other websites can be cached. This kind of caching is called LRU (least recently used). [You can learn more about local caching here.](https://www.geeksforgeeks.org/web-tech/browser-caching/)

To check what your browser is locally caching, look up, "how to check local cache in ..." your respective browser. I use firefox, so its as simple as typing in the search engine, about:caching.

##### Ask ISP Cache
Each Internet Service Provider has their own domain name resolver service. This is a database caching all the websites that the network processes. This means that even if you did not visit the website, but your friend who lives next dorr did, the mapping will use that cache provided by the ISP.

##### Ask name servers
Name servers are responsible for keeping track of countless domain names, and these servers are around the globe.

A name server follos a hierarchy.
1. Root servers.
2. TLD servers.
3. Host name servers.

The ISP sends a message to the root server, requesting a specific TLD.

The root server responds with an IP address to a TLD server handling the requested TLD.

The ISP then sends a message to the TLD server, requesting a specific domain name.

The TLD server responds with an IP address to the host name server containing that specific domain name.

Lastly, the ISP sends a message to the host name server, requesting the exact url the user typed in.

The host name server responds with the exact IP address to the resource.

The ISP responds back to the initial client that was requesting the resource, and then we  can connect to the computer storing the domain.

This process is rather rare as tons of information is stored along the way. But when it does happen, multiple name servers can respond to the ISP's requests. This helps with cases when routing traffic is congested or a name server is down.

### Hypertext Transfer Protocol
The hypertext transfer protocol (http for short) is the protocol responsible for fetching a resource like a webpage, so that your browser can download the resource and render it.

In the URL, it comes at the beginning of the text. This is called a scheme and there are other protocols that the scheme can use than just http.

Lets look at the process of using http.
1. Direct browser to URL.
2. Browser looks up IP address.
3. Browser sends an http request.
4. host sends an http response.
5. Browser renders response.

#### Direct Browser to URL
We use a browser to type an URL into a search engine, or to click a hyperlink in an already opened webpage.

In whatever case, we are using an URL to do so.

The URl has a scheme at the beginning which dictates what protocol the browser must use in order to fetch the resource at that URL. The two most common are:
* http.
* https.

#### Browser Looks Up IP Address
Once we have the URL, the browser must use a DNS resolver to map the human readable name to an IP address.

#### Browser Sends an Http Request
Once the browser has located the IP address of the computer hosting the requested URL, the browser sends an http request to fetch the resource.

##### Brief Http Request Structure
An http request can be as minimal as having 2 sections.
* GET /essay777.html HTTP/1.1.
* Host: www.educationofwriting.com.

The first line starts with an http verb, GET in this case. GET tells the reciever that we are fetching a resource. There are other http verbs like post, telling the reciever we are putting something on the web.

The first line continues with a /essay777.html, the path to the specific resource on the website.

Finally, the first line concludes with the protocol and the version that is being used to fetch the resource, HTTP/1.1.

The second line contains the domain name of the URL. This is required because most hosts store many websites.

#### Host Sends an Http Response
Once the host computer recieves the http request, it sends back an http response containing the content of the resource and its metadata back to the sender (client).

The content is the actual resource being requested For example,. if the request was a document, the content would be written in an html document.

##### Brief Http Response Structure
* HTTP/1.1 200 OK.

The beginning is the protocol being used to fetch the resource.

The following after the protocol is the status code determining if the request to retrieve the document was successful or a failure.

Another part to http responses are headers. Headers provide additional information to browsers and help with rendering the content.
* Content-Type: text/html; charset=UTF-8.
* Content-Length: 208.

The content type tells  the browser what kind of data is being sent back. Is it a text, image, video, javascript, etc. The charset is how the text encoding should be handled.

The content length tells the browser how large the resource is in bytes, helping the browser estimate download time of the resource.

#### Browser Renders Response
Once the http response is recieved, the browser can then render the webpage to its user.

#### HTTP and TCP/IP
The http is   built on top of the IP at the application layer, the topmost layer.

The http requests and http responses are nested in IP packets. It is more common for http responses to be in more than one IP packet.

Alternative protocols that are atop of the TCP/IP include but is not limited to:
* emails use: SMTP, POP, IMAP.
* uploading files use: FTP.

## Summary
The world wide web is a collection of resources built atop of the internet. We use web browsers to access the world wide web and retrieve the resources through URLS. This is only made possible as a result of the web browser application following protocols that are atop of the Internet Protocol.
The domain name system maps IP addresses to human readable names that you and I use to navigate the world wide web everyday. The mapping process can be as simple as recieving the IP address of the domain name from the local caching database, an ISP's DNR service, or as complex as the ISP reaching out to name servers to find the mapping of an domain name to its IP address.
Web browsers use a protocol layered atop of TCP/IP to exchange data over the web. The Hypertext transfer protocol is just one flavor and helps the browser fetch and download a resource, allowing the browser to render the page at the particular URL.