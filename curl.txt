Curl - is a tool to transfer data from or to a server.

Sample Get method:
curl localhost:3000

POST method: 
curl localhost:3000/post -X POST -H "Content-Type: application/json" \
  -d '{"post": "My first Post!"}'

Display the headers:
curl -v localhost:3000

Response:
Note: Unnecessary use of -X or --request, POST is already inferred.
*   Trying ::1:3000...
* connect to ::1 port 3000 failed: Connection refused
*   Trying 127.0.0.1:3000...
* Connected to localhost (127.0.0.1) port 3000 (#0)
> POST /post HTTP/1.1
> Host: localhost:3000
> User-Agent: curl/7.76.1
> Accept: */*
> Content-Type: application/json
> Content-Length: 30
>
* Mark bundle as not supporting multiuse
< HTTP/1.1 200 OK
< content-type: text/html; charset=utf-8
< cache-control: no-cache
< content-length: 16
< Date: Mon, 07 Jun 2021 01:06:05 GMT
< Connection: keep-alive
< Keep-Alive: timeout=5
<
* Connection #0 to host localhost left intact
Blog post added!

Uploading files, simply add @ symbol before the file location:
curl -X POST -F 'image=@/home/user/Pictures/wallpaper.jpg' http://example.com/upload
