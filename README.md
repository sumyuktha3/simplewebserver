# Developing a Simple Webserver
## AIM:
To develop a simple webserver to serve html pages.

## DESIGN STEPS:
### Step 1: 
HTML content creation
### Step 2:
Design of webserver workflow
### Step 3:
Implementation using Python code
### Step 4:
Serving the HTML pages.
### Step 5:
Testing the webserver

## PROGRAM:
## mywebserver.py
```
from http.server import HTTPServer,BaseHTTPRequestHandler

Content="""
<!doctype html>
<html>
<head>
<title>my webserver</title>
</head>
<body>
<h1>MULTIPLICATION TABLES OF 3</h1>
4×0=0<br>
3×1=3<br>
3×2=6<br>
3×3=9<br>
3×4=12<br>
3×5=15<br>
3×6=18<br>
3×7=21<br>
3×8=24<br>
3×9=27<br>
3×10=30<br>
</body>
</html>
"""

class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request recived")

        self.send_response(200)
        self.send_header('content-type','text/html; charset=utf-8')             
        self.end_headers()

     #to send the responce
        self.wfile.write(Content.encode())

 #to create server address     
server_address=('',80)

#to listen at the specified port
httpd = HTTPServer(server_address,myhandler)
print("MY WEBSERVER IS RUNNING...")
httpd.serve_forever()

```
## OUTPUT:

![output](./static/img/i.JPG)

![output](./static/img/i1.JPG)

## RESULT:
Thus, a webserver is designed to display multiplication table and is hosted in the URL
http://sumyuktha.student.saveetha.in/