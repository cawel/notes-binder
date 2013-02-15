# curl

## Examples:
* GET
  * curl www.google.ca
* HEAD
  * curl -I www.google.ca
  * curl -I 'http://example.com/bags/list?quantity=5&type=laptop+messenger'
* POST
  * curl -k -F id=124 -F type='laptop messenger' -F size='large' https://t2feed.herokuapp.com/bags/create
  * curl -d "userName=my_username;otherField=many words in this field" http://example.com/page.php

## Common options
* -I/--head (HTTP/FTP/FILE) 
  * Fetch the HTTP-header only! HTTP-servers feature the command HEAD which this uses to get nothing but the header of a document.
  * note: this will issue a HEAD request, e.g. "HEAD /webpage HTTP/1.1"
*  -k/--insecure (SSL) 
  * This option explicitly allows curl to perform "insecure" SSL connections and transfers. All SSL connections are attempted to be made secure by using the CA certificate bundle installed by default. This makes  all  connections  considered  "insecure"  fail unless -k/--insecure is used.
* -F/--form <name=content>
  * (HTTP) This lets curl emulate a filled-in form in which a user has pressed the submit button. This causes curl to POST data  using the Content-Type *multipart/form-data* according to RFC2388.
* -X/--request <command>
  * (HTTP) Specifies a custom request method to use when communicating with the HTTP server. The specified request will be used instead of the method otherwise used (which defaults to GET).
* -d/--data <data>
  * (HTTP) Sends the specified data in a POST request to the HTTP server, in the same way that a browser does when a user  has  filled in an HTML form and presses the submit button. This will cause curl to pass the data to the server using the content-type *application/x-www-form-urlencoded*.
  * note: curl will not do the url-encoding for you.
