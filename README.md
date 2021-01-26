# How Web Works Exercise
## Part One: Solidify Terminology

In your own terms, define the following terms:
1. **What is HTTP?** http and https are protocols. http stands for **H**yper**t**ext **T**ransfer **P**rotocol and https is the secured / encrypted version. The protocol defines how resources and documents are obtained between various resources. ftp is an example of another protocol.
1. **What is a URL?** **U**niversal **R**esource **L**ocator, or in human-speak, 'the web address'. The web address is composed of the protocol (http or https) the hostname, the resource or document you wish to communicate with, and finally any additional rot needed to complete the request. **hostname** is the company or site -- this part of the url typically ends with the .com, .org, .edu identifier. **resource** is the particular part or document you wish to retrieve. Sometimes the resource may require additional information and this information is indicated with the by information strings that follow a **?** in the url. 
1. **What is DNS?** **D**omain **N**ame **S**ervice -- the 'phone book' for the web. It turns resolves www.springboard.com into an ip address so the http protocol knows where to send the data packets, much like the way you look up a business in a phone book and you get a phone number that you need to call.
1. **What is a query string?** **query string** is the additional rot that exists in a url that is to the right of the **?** in the url. The strings are typically additional values that the resource may need to facilitate a connection, identify a user, pass in customizations, etc. These are key=value pairs and special characters like a space are changed to %20. The server needs logic to process and use this additional information. The query string has no affect when there is nothing on the server to interpret the query string.
1. **What are two HTTP verbs and how are they different?** Two sample verbs are **GET** and **POST**. **GET** is a read-only request for information. The server is sending you information to fulfill your request, but the server does not change anything that is stored on the server. **POST** on the otherhand, are requests that may change things / information on the server. Submitting a form with a new user and password is a POST that will cause the server to create a new user with the password. The exchange of information is within the submitted form -- you should not see 
https://boa.com/myaccount?user=carelessbanker&password=abc123 
as the url when making a post request. Other [verbs/methods](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods) are **HEAD**, **PUT**, **DELETE**, **CONNECT**, **OPTIONS**, **TRACE**, and **PATCH**.
1. **What is an HTTP request?**
   * An **HTTP request** is a request for information from a server. The request includes the method / verb GET, the protocol, the resource we are requesting information from. 
1. **What is an HTTP response?**
   * An **HTTP response** is a response from the server with the information that was requested. The response includes any pertinant headers, a status code (200 is good), and the data that satisifies the request.
1. **What is an HTTP header? Give a couple examples of request and response headers you have seen.**
   * An **HTTP header** contains additional information that the client and server may pass along to each other with the request. A header may include hostname information, language information (language the client browswer would like for the response), date according to the client browser, any cookies
   * Sample request header:
   ```
    Host: icanhazdadjoke.com
    user-agent: curl/7.73.0
    accept: */*

   ```

   * Sample response header:
   ```
    Server: Cowboy
    Connection: keep-alive
    X-Powered-By: Express
    Access-Control-Allow-Origin: *
    Content-Type: application/json; charset=utf-8
    Content-Length: 2003
    Etag: W/"7d3-SOGVmDZGKzQwRlUBCYZFqg5P/EY"
    Date: Tue, 26 Jan 2021 01:25:25 GMT
    Via: 1.1 vegur
   ```

1. **What are the processes that happen when you type “http://somesite.com/some/page.html” into a browser?**
   * Protocol is --http--, site is --somesite.com--, requested resource is --/some/page.html--
   * DNS converts --somesite.com-- into an IP address and connects to the server with the default port.
   * resource --some/page.html-- is located (or dynamically created) by the web server and the requested resource is sent back to the client in the form of a response.
   * client browser and related software parse the response and present the data in the client's web browser.


## Part Two: Practice Tools

1. Using --**curl**--, make a --**GET**-- request to the --icanhazdadjoke.com-- API to find all jokes involving the word “pirate”.
   ```
   { [295 bytes data]
100   295  100   295    0     0   1260      0 --:--:-- --:--:-- --:--:--  1260What does a pirate pay for his corn? A buccaneer!
What did the pirate say on his 80th birthday? Aye Matey!
Why couldn't the kid see the pirate movie? Because it was rated arrr!
Why do pirates not know the alphabet? They always get stuck at "C".
Why are pirates called pirates? Because they arrr!
* Connection #0 to host icanhazdadjoke.com left intact
   ``` 

1. Use --**dig**-- to find what the IP address is for --icanhazdadjoke.com--. 
   * dig . . what can I say about dig? Hmmm, how about either put a note that Window users will be poorly supported by Springboars, remove mention of dig from your . . rithm's course .. or maybe have someone in Springboard validate the information instead of pointing to a document that points to a site that points you to another site? I know in the 'real world' things happen, sites change, we need to read manuals and find solutions, but not in an education environment where you reference the use and then actually craft a question that uses the tool that can't get installed?  
   * The IP address, via --**curl**--, is 104.21.91.232 port 443. 

1. Make a simple web page and serve it using --**python3 -m http.server**--. Visit the page in a browser. 
   * NOT EVERYONE IN YOUR CURRICULUM USES A MAC.
   * I find it poor that this question exists. Does anyone at Springboard review the Rithm School curriculum and how Springboard fits into it? This question is asked in Unit 14 and Springboard does not start Python until unit 18. Need I say more? I am critical on this one because of the needless boondoggle from the 'dig' command / install of Bind because Springboard offered instructions on how to install Bind, but nobody at Springboard has taken the time to ensure the directions in their ['We're sorry you are using windows-gram'](https://ddf46429.springboard.com/uploads/resources/1601665902_Git_Bash_Documentation.pdf) are accurate and work (_HINT_ - they do not).   


## Part Three: Explore Dev Tools

Build a very simple HTML form that uses the GET method (it can use the same page URL for the action) when the form is submitted.

Add a field or two to the form and, after submitting it, explore in Chrome Developer tools how you can view the request and response headers.

Edit the page to change the form type to POST, refresh in the browser and re-submit. Do you still see the field in the query string? Explore in Chrome how you can view the request and response headers, as well as the form data.


## Part Four: Explore the URL API

At times, it’s useful for your JavaScript to look at the URL of the browser window and change how the script works depending on parts of that (particularly the query string).

Read about the [URL API](https://developer.mozilla.org/en-US/docs/Web/API/URL)

Try some of the code examples in the Chrome Console so that you can get comfortable with the basic methods and properties for instances of the URL class.
