# API Endpoints

OOGY in Postman 

OOGy service have 7 API’s. 

Below we explain each with the help of postman. 

Browse OOGY 

We can browse (API URL)/greeting to know is that service is running or down. 

 

## Login 

Login api return you token for next step. login api verify your credentials.  

API Type is POST 

Api url will be (API URL)/login 

Header key will be (Content-Type ) and value ( application/json ) 

 

Body tab will open sub type. 

In Sub type select raw 

And JSON (application/json) 

Now right json inside body with following 3 credentials. 

serverid: moca server id to determine connection URL other credentials. 

username : moca server connection username 

password : moca server connection password 

 

when you click on send button following json will return 

MocaStatusCode : it will return moca status code 0 if all goes fine. 

ErrorMessage: it will return error message if any 

StatusDescription : Message from service . if login goes fine User logged in successfully. Otherwise empty  

payload 

session_key : which you use for next step to execute command and logout. 

Results : results will be null in login 

 

 

 

 

## Execute 

Execute APi actually run your queries and command and give you output in json form 

Method type Post 

Api url will be (API URL)/execute. 

3)Header tab contain only one key. Header key will be  ( Content-Type ) and value ( application/json ) 

 

4) Body tab will open sub type 

5) In Sub type select raw 

      6) And JSON (application/json) 

Now right json inside body with following 5 credentials 

command: Command or query  

serverid: Command or  moca server id to determine connection URL other credentials 

username (Optional): moca server connection username  

password (Optional): moca server connection password 

session_key (Optional): Session id which returned in login. 

Send username password or session_key or send all credentials 

 

when you click on send button following json will return 

 

 

MocaStatusCode : it will return moca status code 0 if all goes fine. 

ErrorMessage: it will return error message if any 

StatusDescription : Message from service . if login goes fine User logged in successfully. Otherwise empty  

payload 

session_key : which you use for next step to execute command and logout. 

Results : results contain all data return from the query 

 

 

 

 

## Logout 

Login api return you token for next step . login api verify your credentials .  

API Type is Post 

Api url will be (API URL)/logout 

Send following 3 parameter with query string  as shown 

username : moca server connection username 

session_key: key which was return in login in session_key 

serverid: moca server connection url 

 

 

 

 

 

 

## Hello World 

Login api return you token for next step . login api verify your credentials .  

API Type is Post 

Api url will be (API URL)/helloworld 

Send following 3 parameter with querystring  as shown 

3)Header tab contain only one key. Header key will be  ( Content-Type ) and value ( application/json ) 

4) Body tab will open sub type 

5) In Sub type select raw 

      6) And JSON (application/json) 

Now right json inside body with following 3 credentials 

serverid: Command or  moca server id to determine connection URL other credentials 

username (Optional): moca server connection username  

password (Optional): moca server connection password  

session_key (Optional): Session id which returned in login. 

Send username password or session_key or send all credentials 

 

 

## API Router 

A generic Proxy to pass through and call any URL including APIs from Moca. 

Use cases: 

Java 6 is installed on RP Server, and it does not support TLS 1.1 and above. The API Router can be called directly from Moca, as it does support TLS 1.0, and it can make the request on behalf of the RP server in the required TLS Mode. 

Consolidate logic and create a single method in RP that routes all third party calls to external systems via API Router 

Detail 

API Type is Post 

Api url will be (API URL)/apirouter 

Body tab will open sub type 

In Sub type select raw 

And JSON (application/json) 

The body must contain the following parameters 

URL: URL for the API 

httpmethod: moca server connection username  

queryparameters[]: Array to hold key/value pair for query string. 

headerparameters[]: Array to hold key/value pair for header request parameters. 

Body: Body content that will be sent to the URL defined above. 

Graphical user interface, text

Description automatically generated 

 

 

 

## Post Download 

Login api return you token for next step . login api verify your credentials .  

API Type is Post 

Api url will be (API URL)/postdownload 

Send following 3 parameter with querystring  as shown 

3)Header tab contain only one key. Header key will be  ( Content-Type ) and value ( application/json ) 

4) Body tab will open sub type 

5) In Sub type select raw 

      6) And JSON (application/json) 

Now right json inside body with following 3 credentials 

serverid: Command or  moca server id to determine connection URL other credentials 

username (Optional): moca server connection username  

password (Optional): moca server connection password 

session_key (Optional): Session id which returned in login. 

Send username password or session_key or send all credentials 

data : data 

dwnld_info : download info 

run_tran_flg : flag of transaction 

when you click on send button following json will return 

 

 

MocaStatusCode : it will return moca status code 0 if all goes fine. 

ErrorMessage: it will return error message if any 

StatusDescription : Message from service . if login goes fine User logged in successfully. Otherwise empty  

payload 

session_key : which you use for next step to execute command and logout. 

Results : results contain all data return from the query 

 

 

 

## POST DOWNLOAD XML 

Login api return you token for next step . login api verify your credentials .  

1)API Type is Post 

2)Api url will be (API URL)/postdownloadxml 

Send following 3 parameter with query string  as shown 

3)Header tab contain only one key. Header key will be  ( Content-Type ) and value ( application/json ) 

4) Body tab will open sub type 

5) In Sub type select raw / XML 

      6) And xml (application/xml) 

7)Now right header with following 8 credentials 

serverid: Command or  moca server id to determine connection URL other credentials 

username (Optional): moca server connection username  

password (Optional): moca server connection password 

session_key (Optional): Session id which returned in login. 

Send username password or session_key or send all credentials 

data : data 

dwnld_info : download info 

run_tran_flg : flag of transaction  

 

XML is in body 