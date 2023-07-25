# springboot-rest-blog Intro
REpresentional State Transfer API (Application programming interface) for a Blog.
-REpresentional means formats (xml, json,yaml,html,ecc.)
-State means data
-Transfer means carry data betwen consumer and provider using HTTP protocol

# Architecture
|  Client  |  --HTTP Request (json)---> |  Server  |  <------> | Database |
|(Consumer)| <---HTTP Response ----     |(Rest API)|           | Postgres |

# Constranints
- client-server architecture= The client is the FE and the server is the BE of the service.
- Stateless=  All state info should be kept on client side. No data should be stored on the server.
  Each request must contain all of the information necessary to be understood by the server
- Cacheable= The client should have the ability to store the response in a cache. This improve 
  the performance of the API 
- Uniform Interface= A generic interface to mangae all the interactions
- Layered System= The server can have multiple layers

# Concept
-Resource= is what exposed to outer world, through your app. For a Blog are:
1. Post
2. Comment
3. User
4. Tags

# Resource
The resources are be identified by a URI (Uniform Resource Identifier). Ex:
- GET http://lcoalhost:8000/api/posts/ Return all the posts
- GET http://lcoalhost:8000/api/posts/2 Return the post with id=2
- POST http://lcoalhost:8000/api/posts/ Create a post
- PUT http://lcoalhost:8000/api/posts/2 Modify the post with id=2
- DELETE http://lcoalhost:8000/api/posts/2 Delete the post with id=2

# Sub-Resource
- GET resource\{post-id}\sub-resource\{comment-id}
Ex:
- GET posts\{post-id}\comments\{comment-id}

# HTTP status code
- 200 OK = The request is successfull and the response in returned to the client
- 201 Created = The request is successfull and a new resource is created
- 400 Bad Request = The server failed to process the request
- 401 Unauthorize = Authentication is required for the resource
- 403 Forbidden = The server is refusing the response
- 404 Not Found = The request resource is not found
- 500 Internal Server Error = Generic Error Message





